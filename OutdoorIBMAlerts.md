## Outdoor IBM Alerts
- 2 types of azure functions are used here:
  - HttpTriggerOutdoorAlerts
  - TimerTriggerOutdoorAlerts

### HttpTriggerOutdoorAlerts

  - For IBM Outdoor process, at the end of monthly outdoor calculation process, this function is called.
  - As the outdoor data is getting updated from the databricks every hour, after the process is completed **HttpTriggerOutdoorAlerts** function is invoked.
  - Airqualityrange(aqr) is a static table in which IAQ Score is defined.
  - For HttpTriggerOutdoorAlerts function, the target tables are MonitoringSiteIBM and OutdoorAirQualityDevice table.
  - From Alerts table, determine all the alerts where alertType='Outdoor'and isdeleted=0 and regon='US'
  - Iterate for each alert(alertId) and invoke the stored procedure '**usp_OutdoorAirQuality_Notifications**' with input as 'alertid'.
  - Retrieve the following alert details from alert table for the alertid: alertid,alerttype,parameterName,alertNotificationText,alertNotificationTextFr,minthreshold,maxthreshold,nominthreshold,nomaxthreshold, improvementThreshold and alertFrequency
  - Whatever alerts eligible are associated for outdoor will be generated from this function which is indirectly using the stored procedure (**usp_OutdoorAirQuality_Notifications**) and populate the AccountAlerts table.
  
  **For Normal Alerts**
  - For every normal alert there is a respective improvement alert.
  - Based on data in MonitoringSiteIBM msi , outdoorAirQualityDevice oad (msi.cityName =oad.userCity and msi.State = oad.userState), aa_user aau (aau.accountID = oad.accountID) and alerts al table, insert eligible records into accountalerts table which satisfies the below conditions:
    - Aqi between AQI Poor minimum threshold(100.50) and Very Poor Max Threshold(200.49) : **msi.aqi >=@minthreshold and msi.aqi <= @maxthreshold**
	- Internally, Poor(100.50 to 150.49) and Very Poor(150.50 to 200.49) range must be considered as one range Poor-Very Poor
	- aau.airQualityNotificationEnabled = 'true' and oad.activeflag = 1.
	- Check and ensure latest alert record for the state, city, accountId and alertId is improvementalert & the latest normal alert sent is more than alert.alertFrequency 60 minutes.
	- Insert data in accountalerts from outdooor table oad.userCity, oad.userState, oad.accountId.
	
  **For Deterioration Alerts**
  - Based on data in MonitoringSiteIBM msi , outdoorAirQualityDevice oad (msi.cityName = oad.userCity and msi.State = oad.userState), aa_user aau (aau.accountID = oad.accountID) and alerts al table, insert eligible records into accountalerts table which satisfies below conditions:
    - Aqi within AQI Severe threshold(200.50 to 500) : **msi.aqi >= @nominthreshold and msi.aqi <= @nomaxthreshold**, which is the severe range for AQI from AirQualityRange table.
	- aau.airQualityNotificationEnabled = 'true' and oad.activeflag = 1.
	- Check and ensure latest alert record for the state, city, accountId and alertId is improvementalert. If the latest alert sent is improvement alert, then ensure that latest normal alert sent is more than alert.alertFrequency 60 minutes.
	- Insert data in accountalerts from outdooor table oad.userCity, oad.userState, oad.accountId.
	
  **For Improvemnt Alert**
  - Based on data in MonitoringSiteIBM msi , outdoorAirQualityDevice oad (msi.cityName = oad.userCity and msi.State = oad.userState), aa_user aau (aau.accountID = oad.accountID) and alerts al table, insert eligible records into accountalerts table which satisfies below conditions:
    - Aqi within AQI Good threshold : msi.aqi <= improvementThreshold.
	- aau.airQualityNotificationEnabled = 'true' and oad.activeflag = 1
	- Ensure the latest record for the alertid, accountId, state and city is Normal or Deterioration alerts.
	- Insert data in accountalerts from outdooor table oad.userCity, oad.userState, oad.accountId.
  - If any exception occurs, then return to the function with a failure message, otherwise, return to the function with a success result.
  - If result is success, then log the function execution record into AzureFuntionLog table as 'success' and exit.  
  - If result is not success, then send an email notifying process failure, to take an action and log the function execution record into AzureFuntionLog table as 'failure' with result message.

### TimerTriggerOutdoorAlerts
  - This function looks for the pending alerts from the AccountAlerts with sentFlag='false'. It retrieves the data and sends to the respective users. But internally, it is handle to send notification in between 11 am to 9 pm CST.
  - For every alerts, the end user might be an android or iOS user.
  - For every user there is a deviceTag, which relates the device to the IoTHub. Based on this, the notification hub is going to identify the device(iOS or android) and send the respective notification payload.
  - Following are the main columns to be fetched:  alertid, alerttitle, alertNotificationText, deviceTag, accountId etc.
  - Get iosNotificationsEnabled and androidNotificationsEnabled values from 'aa_user' table.
  - Get alertNotificationText based on messageCategoryId in accountAlerts and language of user in aa_user tables:
	- If messageCategoryId is null, if aa_user.language is ‘en’ then get alert.alertNotificationText or get alert. alertNotificationTextFr  if user.language is ‘fr’.
    - If messageCategoryId is not null, then get either notificationText  or notificationTextfr from MessageCategory table based on messageCategoryId and aa_user.language value (en or fr).

  - Based on iosNotificationsEnabled and androidNotificationsEnabled values, send notifications. Following are message formats for android and ios respectively:
    - Android : {"data":{"title":"Alert-Title","message":"Alert-Message","badge":Badge-Count,"screen":"Alert-Type","deviceID":"DeviceId"}}
	- iOS : {"aps":{"alert":{"title":"Alert-Title","body":"Alert-Message"},"badge":Badge-Count},"screen":"Alert-Type","deviceID":"DeviceId"}
	  - **Badge:** Get the count of all the unread alerts for the respective account where sentflag = 1 and isRead = 0 and isActive = 1 and deviceStatus = ‘Active’.
	  - **Screen:** filter/outdoor/indoor/generic/Adhoc  are the screen values in the message format.
  - Get all the invalid alerts into a list ‘lstInvalidAlerts’.
  -	Remove the invalid alerts from main list ‘outdoorAlerts’.
  - Iterare the list ‘outdoorAlerts’ and send notifications as below:
    - Validate accountalerts.deviceTag for hexadecimal check
	- Update notification text placeholder: #city and #state with the respective values.
	- Based on iosNotificationsEnabled and androidNotificationsEnabled values, send notifications. While sending notification, need to get realtime badge count, so need to follow the below approach:
	  - Update the table ‘BadgeCount’ and lock the transaction on it.
	  - Get the count of all unread and sent alerts for the respective account: where sentflag = 1 and isRead = 0 and isActive = 1 and deviceStatus = ‘Active’.
	  - Replace the resultant count with “Badge-Count” integer in the json payload.
	  - Send the notification.
	  - Unlock the table ‘BadgeCount’ by commiting the transaction.
	- While sending notification, if the message contains double quotes (“), removing it from message as the notification hub will thrown an exception and notification will not be sent. 
	- On notification sent successfully, update below columns in AccountAlerts table:  SentFlag=true, alertTS = currentTS , modifiedTS = currents and alertNotificationText = alertNotificationText.
	- For any exceptions/invalid deviceTag, update the below columns in AccountAlerts table: ErrorCode = ‘Exception’, AttemptsRetry = AttemptsRetry+1 and NextTimeToRetry.