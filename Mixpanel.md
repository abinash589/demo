## MixPanel API and Events

**Following are the Mixpanel API call information for getting the response:**
||||
| :- | :- | :-: |
|**URL**|https://data.mixpanel.com/api/2.0/export ||
|**Input Parameters**|from_date|yyyy-mm-dd|
||to_date|yyyy-mm-dd|
||Event|["Event_name"]|
|**Response**|JSON||

**Following are the Event Name to be passed in Mixpanel API for getting the responses:**
|**Event**|**Description**|
|:-|:-:|
|Accept user agreement||
|Alert opened||
|Amazon one time||
|App open||
|Brightness||
|Buy replacement||
|Call support on error||
|Change email||
|Change email incomplete||
|Change password||
|Coming soon learn more||
|Data gap with access to location||
|Data gap with no access to location||
|Delete Filter|Give the responses on the filter deleted|
|Delete property||
|Device created||
|Device not listed||
|Device offline|Give the responses on the offline device |
|Device offline troubleshoot||
|Device removed|Give the responses on the removed device|
|DRS error||
|DRS sign up begin||
|DRS teaser seen||
|Edit profile||
|Email Validated||
|Fan speed||
|FAQs opened||
|FFS property flow canceled||
|FFS property flow completed||
|FFS property flow started||
|Filter added||
|Filter pairing canceled||
|Filter selected||
|Filter type selected||
|First Log in||
|Found RAP model||
|Geofence created||
|Graph opened||
|Graph page view||
|Graph tab view||
|Graph view duration||
|Help||
|Info page reading time||
|Learn more page is opened||
|Learn more question opened||
|Location error||
|Location not found||
|Location not right now alert||
|Location permission set||
|Location permission skipped||
|Log in||
|Log out||
|Missing product image||
|My air location soft ask||
|Network connection||
|Network selected||
|Networks available||
|New device||
|Notification permission||
|Only while using permission update||
|Outdoor added||
|Outdoor deleted||
|Pairing with sensor||
|Pollutant Selected||
|Pollutant selected||
|Power mode||
|Pressed buy||
|Problematic UPC found||
|Product family||
|Property created||
|Property flow cancelled||
|Property naming||
|Provisioning call support||
|Provisioning error||
|Provisioning flow BLE connecting||
|Provisioning flow BLE searching||
|Provisioning flow canceled||
|Provisioning flow started||
|Provisioning help needed||
|Pull to refresh||
|Pull to refresh sensor connection||
|Pull to refresh toasts||
|Push notification opened||
|Push notification soft ask||
|Rename property||
|Replaced filter||
|Replaced with Smart filter||
|Replacement instructions||
|Resend||
|Retailer selected||
|Room already exists||
|Room name changed||
|Room naming||
|Screen home indoor select||
|Screen view||
|Search for address||
|Searching for sensor||
|Sensor data collection info||
|Sensor data received with sample||
|Sensor found||
|Sensor powercycled||
|Sensor throttling||
|Shortcut added||
|Sign up||
|Size selected||
|Smart filter pairing location soft ask||
|Smart filter pairing start||
|Smart filter scanned||
|SRAP provisioning location soft ask||
|Start scanning||
|Tapping x||
|Timer||
|Tip opened||
|Widget activation||
|Widget added||
|Widget uninstall||
|Works with finished||
|Works with opened||
|Works with started||

**Sample Input parameters and responses from the Mixpanel are given below:**
||||
|:-|:-|:-:|
|**URL**|https://data.mixpanel.com/api/2.0/export ||
|**Input Parameters**|from_date|2020-12-29|
||to_date|2020-12-31|
||Event|["Accept user agreement"] |
|**Response**||

<table>
<tr>
<td><b>URL</b></td> <td>https://data.mixpanel.com/api/2.0/export</td><td></td>
</tr>
<tr>
<td><b>Input Parameters</b></td> <td>from_date</td> <td>2020-12-29</td>
</tr>
<tr>
<td></td> <td>to_date</td> <td>2020-12-31</td>
</tr>
<tr>
<td></td> <td>Event</td> <td>["Accept user agreement"]</td>
</tr>
<tr>
<td><b>Response</b></td>
<td>
^ Extra blank line above!
```json
{
  "event": "Accept user agreement",
  "properties": {
    "time": 1609420266,
    "distinct_id": "849DBA18-C0AB-4A49-9A23-B5434834A238",
    "$app_build_number": "1.12.0.4522",
    "$app_version_string": "1.12.0",
    "$carrier": "Verizon",
    "$city": "Meridian",
    "$device_id": "849DBA18-C0AB-4A49-9A23-B5434834A238",
    "$insert_id": "f9c260a69955289f",
    "$lib_version": "2.7.7",
    "$manufacturer": "Apple",
    "$model": "iPhone10,3",
    "$os": "iOS",
    "$os_version": "14.2",
    "$radio": "LTE",
    "$region": "Idaho",
    "$screen_height": 812,
    "$screen_width": 375,
    "$wifi": true,
    "Status": "accept",
    "mp_country_code": "US",
    "mp_lib": "swift",
    "mp_processing_time_ms": 1609449079378
  }
}
```
V Extra blank line below!
</td><td></td>
</tr>
</table>