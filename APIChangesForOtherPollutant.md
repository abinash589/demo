### Preface
- The purpose of this document is to add some more response fields(SO2, O3, NO2, CO) to the existing outdoor air quality device API that will be used by mobile app to interact with the backend.
- The goal is to expose some API endpoints that the app will consume.
- API parameters will be added or removed if necessary in a later stage, this will be a part of the development lifecycle.

### API Endpoints
- For the sake of simplicity, we consider that one user will have an associated account that will be made available for later use.
- One account will have multiple locations, each location will have multiple outdoor devices.
- All API endpoints will have 2 additional header fields, one for Language and another for Region.
  - Language: string    "en"|"fr"
  - Region: string      "US"|"CA"
  The default value for Language will be English(en) and for Region it will be United States(US). If the language is French(fr), then all string values will be in French, if French language values are available, otherwise they will be in English. Note the API parameter names and tags will only be in English.
- All API endpoints will also have additional header fields to indicate the OS type and App version.

### GetOutdoorAirQualityDeviceData
- **Description:**
  - Gets the current values for the air quality parameters for the specified outdoor device.
  - If the optional latitude and longitude is specified it is considered a current location and is mapped to a city and state and the air quality parameters for that location are returned.
- **Method:** GET
- **Header:**
  - Ocp-Apim-Subscription-Key: String
  - Authorization: String 	"Bearer <access_token>"
  - Language: String	"en"|"fr"
  - Region: String		"US"|"CA"
  - OSType: String		"ios"|"android"
  - AppVersion: String	ex- 2.0.0.119
  - Version: "4.0"
- **Input Parameters:**
  - outdoorDeviceID
  - latitude *(optional)*
  - longitude *(optional)*
- **Responses:**
  - 200 	Success- Response:
```javascript
{
	"deviceID":"5231",
	"city":"Kansas City",
	"state":"KS",
	"country":"United States",
	"latitude":39.11417,
	"longitude":-94.62746,
	"lastUploadTS":"2021-07-27T07:00:00-05:00",
	"lastUploadAQI":76.0,
	"lastUploadTemperature":22.0,
	"lastUploadHumidity":81.0,
	"lastUploadPM10":42.0,
	"lastUploadPM2_5":24.0,
	"lastuploadSO2": ,
	"lastUploadO3": ,
	"lastuploadNO2": ,
	"lastuploadCO": 
}
```
	
  - 400     {“reasonCode”: 1, “message”: “Invalid input parameter ”}
  - 401 	Unauthorized
  - 403 	Forbidden


### GetAirQualityHistoricalDataValues
- **Description:**
  - Gets the historical air quality information for the specified device.
  - All parameters supported by the device such as PM 2.5, PM1, PM 10, SO2, O3, NO2 and CO Air Quality Index and temperature values are returned. If some parameters are not supported by the device then those values will not be returned. For ex- PM1 is not supported by outdoor devices, so its value is not returned.
  - Data will be returned by specified period,i.e., "Day", "Month" or "Year". It will be returned as follows:
    - Day (24 hours for the date specfied - aggregated by minute).
	- Month(All days for the year and month specified  - aggregated by day).
	- Year(All months for the year specfied - aggregated by month).
  - For outdoor device, air quality information can be fetched by allowing latitude and longitude instead of deviceID.
- **Method:** GET
- **Header:** 
  - Ocp-Apim-Subscription-Key: String
  - Authorization: String 	"Bearer <access_token>"
  - Language: String	"en"|"fr"
  - Region: String		"US"|"CA"
  - OSType: String		"ios"|"android"
  - AppVersion: String	ex- 2.0.0.119
  - Version: "4.0"
- **Input Parameters:**
  - deviceID
  - deviceType
  - period *(required)*
  - timestamp *(required)*
  - latitude *(optional)*
  - longitude *(optional)*
- **Responses:**
  - 200 	Success- Response:
	
```javascript
if period==day:
{
"deviceID":"5222",
"city":"Texas City",
"state":"TX",
"country":"United States",
"latitude":null,
"longitude":null,
"period":"day",
"data":{
	"channels":["localTimestamp","AQI","PM2_5","PM10","temperature","humidity"],
	"dataList":[["2021-07-27T00:00:00-05:00",26.0,6.0,14.0,29.0,76.0],
				["2021-07-27T01:00:00-05:00",23.0,6.0,13.0,29.0,78.0],
				["2021-07-27T02:00:00-05:00",21.0,5.0,13.0,28.0,79.0],
				["2021-07-27T03:00:00-05:00",20.0,5.0,12.0,28.0,80.0],
				["2021-07-27T04:00:00-05:00",20.0,5.0,12.0,28.0,81.0]]
		}
}
```

```javascript
if period==month:
{
"deviceID":"5222",
"city":"Texas City",
"state":"TX",
"country":"United States",
"latitude":null,
"longitude":null,
"period":"month",
"data":{
	"channels":["localTimestamp","AQI","PM2_5","PM10","temperature","humidity"],
	"dataList":[["2021-07-01T00:00:00-05:00",22.0,5.0,9.0,28.46,72.0],
				["2021-07-02T00:00:00-05:00",18.0,4.0,7.0,28.83,72.0],
				["2021-07-03T00:00:00-05:00",24.0,6.0,9.0,27.42,81.0],
				["2021-07-04T00:00:00-05:00",28.0,7.0,11.0,27.21,81.0],
				["2021-07-05T00:00:00-05:00",18.0,4.0,7.0,27.71,79.0],
				["2021-07-06T00:00:00-05:00",21.0,5.0,8.0,26.38,83.0],
				["2021-07-07T00:00:00-05:00",37.0,9.0,15.0,26.46,77.0],
				["2021-07-08T00:00:00-05:00",42.0,10.0,17.0,26.58,82.0],
				["2021-07-09T00:00:00-05:00",46.0,11.0,19.0,26.08,85.0],
				["2021-07-10T00:00:00-05:00",50.0,13.0,24.0,28.88,80.0],
				["2021-07-11T00:00:00-05:00",68.0,21.0,49.0,28.79,78.0],
				["2021-07-12T00:00:00-05:00",59.0,16.0,46.0,28.29,75.0],
				["2021-07-13T00:00:00-05:00",49.0,12.0,27.0,28.71,72.0],
				["2021-07-14T00:00:00-05:00",28.0,7.0,13.0,28.75,72.0],
				["2021-07-15T00:00:00-05:00",29.0,7.0,13.0,29.0,73.0],
				["2021-07-16T00:00:00-05:00",44.0,11.0,20.0,29.38,72.0],
				["2021-07-17T00:00:00-05:00",36.0,9.0,16.0,29.63,71.0],
				["2021-07-18T00:00:00-05:00",27.0,7.0,12.0,29.54,72.0],
				["2021-07-19T00:00:00-05:00",21.0,5.0,9.0,29.04,75.0],
				["2021-07-20T00:00:00-05:00",26.0,7.0,10.0,26.67,80.0],
				["2021-07-21T00:00:00-05:00",57.0,15.0,22.0,27.71,75.0],
				["2021-07-22T00:00:00-05:00",24.0,6.0,9.0,28.13,76.0],
				["2021-07-23T00:00:00-05:00",30.0,7.0,13.0,30.04,74.0],
				["2021-07-24T00:00:00-05:00",38.0,9.0,23.0,29.58,74.0],
				["2021-07-25T00:00:00-05:00",24.0,6.0,12.0,28.83,76.0],
				["2021-07-26T00:00:00-05:00",23.0,6.0,10.0,29.29,74.0],
				["2021-07-27T00:00:00-05:00",22.0,5.0,13.0,28.4,79.0]]
		}
}
```

```javascript
if period==year:
{
"deviceID":"5234",
"city":"Texas City",
"state":"TX",
"country":"United States",
"latitude":null,
"longitude":null,
"period":"year",
"data":{
	"channels":["localTimestamp","AQI","PM2_5","PM10","temperature","humidity"],
	"dataList":[
			["2021-01-01T00:00:00-06:00",41.0,11.0,17.0,12.69,73.0],
			["2021-02-01T00:00:00-06:00",44.0,12.0,19.0,10.52,81.0],
			["2021-03-01T00:00:00-05:00",44.0,11.0,18.0,17.48,77.0],
			["2021-04-01T00:00:00-05:00",46.0,12.0,19.0,20.45,75.0],
			["2021-05-01T00:00:00-05:00",44.0,11.0,18.0,24.17,80.0],
			["2021-06-01T00:00:00-05:00",38.0,10.0,16.0,28.1,75.0],
			["2021-07-01T00:00:00-05:00",34.0,9.0,16.0,28.27,76.0]]
		}
}
```