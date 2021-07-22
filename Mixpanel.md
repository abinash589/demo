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


```json
json
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


</td><td></td>
</tr>
</table>


<table>
<tr>
<td><b>URL</b></td> <td>https://data.mixpanel.com/api/2.0/export </td><td></td>
</tr>
<tr>
<td><b>Input Parameters</b></td> <td>from_date</td> <td>2020-12-29</td>
</tr>
<tr>
<td></td> <td>to_date</td> <td>2020-12-31</td>
</tr>
<tr>
<td></td> <td>Event</td> <td>["Alert opened"]</td>
</tr>
<tr>
<td><b>Response</b></td>
<td>


```json
json
{
  "event": "Alert opened",
  "properties": {
    "time": 1609274085,
    "distinct_id": "16D83774-01E3-46AD-AD1D-2C73AB954D8A",
    "$app_build_number": "1.12.0.4522",
    "$app_version_string": "1.12.0",
    "$carrier": "Verizon",
    "$city": "Sacramento",
    "$device_id": "16D83774-01E3-46AD-AD1D-2C73AB954D8A",
    "$insert_id": "0876380100eb01b4",
    "$lib_version": "2.7.7",
    "$manufacturer": "Apple",
    "$model": "iPhone10,2",
    "$os": "iOS",
    "$os_version": "14.2",
    "$radio": "LTE",
    "$region": "California",
    "$screen_height": 736,
    "$screen_width": 414,
    "$wifi": true,
    "AlertID": "1587073",
    "DeviceID": "469263",
    "Screen deep-linked": "filter",
    "User email": "ujph1010@yahoo.com",
    "mp_country_code": "US",
    "mp_lib": "swift",
    "mp_processing_time_ms": 1609302925509
  }
}
```


</td><td></td>
</tr>
</table>


<table>
<tr>
<td><b>URL</b></td> <td>https://data.mixpanel.com/api/2.0/export </td><td></td>
</tr>
<tr>
<td><b>Input Parameters</b></td> <td>from_date</td> <td>2020-12-29</td>
</tr>
<tr>
<td></td> <td>to_date</td> <td>2020-12-31</td>
</tr>
<tr>
<td></td> <td>Event</td> <td>["Amazon one time"]</td>
</tr>
<tr>
<td><b>Response</b></td>
<td>


```json
json
{
  "event": "Amazon one time",
  "properties": {
    "time": 1609399132,
    "distinct_id": "4088C1FA-6088-41D6-A1FD-0D17E349030A",
    "$app_build_number": "1.11.4319",
    "$app_version_string": "1.11",
    "$carrier": "T-Mobile",
    "$city": "Lansdowne",
    "$device_id": "4088C1FA-6088-41D6-A1FD-0D17E349030A",
    "$had_persisted_distinct_id": false,
    "$insert_id": "f5450ddbd02af2cd",
    "$lib_version": "2.7.7",
    "$manufacturer": "Apple",
    "$model": "iPhone11,2",
    "$os": "iOS",
    "$os_version": "14.2",
    "$radio": "LTE",
    "$region": "Pennsylvania",
    "$screen_height": 812,
    "$screen_width": 375,
    "$wifi": false,
    "User email": "ivanoksan@yahoo.com",
    "mp_country_code": "US",
    "mp_lib": "swift",
    "mp_processing_time_ms": 1609427961445
  }
}
```


</td><td></td>
</tr>
</table>


<table>
<tr>
<td><b>URL</b></td> <td>https://data.mixpanel.com/api/2.0/export </td><td></td>
</tr>
<tr>
<td><b>Input Parameters</b></td> <td>from_date</td> <td>2020-12-29</td>
</tr>
<tr>
<td></td> <td>to_date</td> <td>2020-12-31</td>
</tr>
<tr>
<td></td> <td>Event</td> <td>["App open"]</td>
</tr>
<tr>
<td><b>Response</b></td>
<td>


```json
json
{
  "event": "App open",
  "properties": {
    "time": 1609369820,
    "distinct_id": "EBCD024A-3970-4915-A719-82DF68DADAA4",
    "$app_build_number": "1.10.3976",
    "$app_version_string": "1.10",
    "$carrier": "AT&T",
    "$city": "Los Angeles",
    "$device_id": "EBCD024A-3970-4915-A719-82DF68DADAA4",
    "$had_persisted_distinct_id": true,
    "$insert_id": "fcdeec64e9999fde",
    "$lib_version": "2.7.7",
    "$manufacturer": "Apple",
    "$model": "iPhone9,4",
    "$os": "iOS",
    "$os_version": "14.3",
    "$radio": "LTE",
    "$region": "California",
    "$screen_height": 736,
    "$screen_width": 414,
    "$wifi": false,
    "App status": "cold start",
    "Bluetooth on": false,
    "Location permission": false,
    "Notification permission status": "Granted",
    "mp_country_code": "US",
    "mp_lib": "swift",
    "mp_processing_time_ms": 1609398639199
  }
}
```


</td><td></td>
</tr>
</table>


<table>
<tr>
<td><b>URL</b></td> <td>https://data.mixpanel.com/api/2.0/export </td><td></td>
</tr>
<tr>
<td><b>Input Parameters</b></td> <td>from_date</td> <td>2020-12-29</td>
</tr>
<tr>
<td></td> <td>to_date</td> <td>2020-12-31</td>
</tr>
<tr>
<td></td> <td>Event</td> <td>["Device offline"]</td>
</tr>
<tr>
<td><b>Response</b></td>
<td>


```json
json
{
  "event": "Device offline",
  "properties": {
    "time": 1609348133,
    "distinct_id": "225CC746-85BE-40CF-A9CC-46A94E0D6AF2",
    "$app_build_number": "1.12.0.4522",
    "$app_version_string": "1.12.0",
    "$carrier": "T-Mobile",
    "$city": "Las Vegas",
    "$device_id": "48B5E9E3-D353-47CC-937B-343420B6B9C1",
    "$distinct_id_before_identity": "324172",
    "$insert_id": "4b9d04bb1df5dfb8",
    "$lib_version": "2.7.7",
    "$manufacturer": "Apple",
    "$model": "iPhone13,4",
    "$os": "iOS",
    "$os_version": "14.3",
    "$radio": "NRNSA",
    "$region": "Nevada",
    "$screen_height": 812,
    "$screen_width": 375,
    "$user_id": "324172",
    "$wifi": true,
    "Device type": "Purpleair",
    "User email": "billm56@aol.com",
    "mp_country_code": "US",
    "mp_lib": "swift",
    "mp_processing_time_ms": 1609376952680
  }
}
```


</td><td></td>
</tr>
</table>


<table>
<tr>
<td><b>URL</b></td> <td>https://data.mixpanel.com/api/2.0/export </td><td></td>
</tr>
<tr>
<td><b>Input Parameters</b></td> <td>from_date</td> <td>2020-12-29</td>
</tr>
<tr>
<td></td> <td>to_date</td> <td>2020-12-31</td>
</tr>
<tr>
<td></td> <td>Event</td> <td>["Delete Filter"]</td>
</tr>
<tr>
<td><b>Response</b></td>
<td>


```json
json
{
  "event": "Delete Filter",
  "properties": {
    "time": 1609392561,
    "distinct_id": "braddu97@gmail.com",
    "$app_build_number": "1.12.0.4522",
    "$app_version_string": "1.12.0",
    "$carrier": "AT&T",
    "$city": "College Station",
    "$device_id": "braddu97@gmail.com",
    "$had_persisted_distinct_id": true,
    "$insert_id": "311720dbfcc475ac",
    "$lib_version": "2.7.7",
    "$manufacturer": "Apple",
    "$model": "iPhone11,8",
    "$os": "iOS",
    "$os_version": "14.3",
    "$radio": "LTE",
    "$region": "Texas",
    "$screen_height": 812,
    "$screen_width": 375,
    "$wifi": true,
    "mp_country_code": "US",
    "mp_lib": "swift",
    "mp_processing_time_ms": 1609421366242
  }
}
```


</td><td></td>
</tr>
</table>


<table>
<tr>
<td><b>URL</b></td> <td>https://data.mixpanel.com/api/2.0/export </td><td></td>
</tr>
<tr>
<td><b>Input Parameters</b></td> <td>from_date</td> <td>2020-12-29</td>
</tr>
<tr>
<td></td> <td>to_date</td> <td>2020-12-31</td>
</tr>
<tr>
<td></td> <td>Event</td> <td>["Device removed"]</td>
</tr>
<tr>
<td><b>Response</b></td>
<td>


```json
json
{
  "event": "Device removed",
  "properties": {
    "time": 1609238558,
    "distinct_id": "10be417a-cd8e-45bc-ae5d-1c723ab3d9fe",
    "$app_build_number": 4213,
    "$app_release": 4213,
    "$app_version": "1.12.0.4213",
    "$app_version_string": "1.12.0.4213",
    "$bluetooth_enabled": false,
    "$bluetooth_version": "ble",
    "$brand": "xiaomi",
    "$carrier": "airtel",
    "$city": "Hyderabad",
    "$device_id": "d791b834-1d4b-4784-9e17-855b38624bae",
    "$distinct_id_before_identity": "346298",
    "$google_play_services": "available",
    "$had_persisted_distinct_id": false,
    "$has_nfc": false,
    "$has_telephone": true,
    "$insert_id": "6481a64e24e4c920",
    "$lib_version": "5.8.4",
    "$manufacturer": "Xiaomi",
    "$model": "Redmi Note 5 Pro",
    "$os": "Android",
    "$os_version": "9",
    "$region": "Telangana",
    "$screen_dpi": 440,
    "$screen_height": 2030,
    "$screen_width": 1080,
    "$user_id": "346298",
    "$wifi": false,
    "API success": true,
    "Device type": "RAP",
    "User email": "rakeshzalavadiya@gmail.com",
    "mp_country_code": "IN",
    "mp_lib": "android",
    "mp_processing_time_ms": 1609267398709
  }
}

```


</td><td></td>
</tr>
</table>


