## Outdoor Pollen and Pollen Forecast
- There are 2 process for pollen data. They are:
  - Pollen Outdoor Process
  - Pollen Forecast Process

### Pollen Outdoor Process
- This process uses an IBM api, **US Pollen Observation**, to get the pollen data and not pollutants data(PM2.5,PM10,PM1).
- The US Pollen Observation api returns the pollen observation content for a valid latitude/longitude coordinate.
- The API will return the index and index description for four pollen types- tree pollen, grass pollen, weed pollen, mold pollen.
- The API supports two languages – English and Spanish for the US.
- Pollen data provided through this API is sourced from trusted third-party organization that collects data from allergist’s offices on weekdays, Monday – Friday, except holidays.
- There are four segments of the data feed. The first contains the metadata, which includes the specified language parameter in the request URL.
- The remaining data segments contain information on the location, reporting date/time and station, the specific tree species, and index for tree pollen, grass pollen, weed pollen, or mold pollen.
- **API URl:** '''https://api.weather.com/v1/geocode/'''+ str(lat) + """/""" + str(long) +'''/observations/pollen.json?language=en-US&apiKey=''' + apiKey
  - Required Parameters: geocode,language, format,apikey
- JSON Response:
```javascript
{"metadata":{
    	"language": "en-US",
    	"transaction_id": "1547239301440:523427864",
    	"version": "1",
    	"latitude": 32.73,
    	"longitude": -117.16,
    	"expire_time_gmt": 1547515441,
    	"status_code": 200
	},
"pollenobservations":[
{"class":"pollenobs",
"loc_id":"ATL",
"loc_nm":"Atlanta",
"loc_st":"GA",
"rpt_dt":"2014-04-08T15:00:00Z",
"process_time_gmt":1396983306,
"treenames":[
{"tree_nm":"Oak"},
{"tree_nm":"Birch"},
{"tree_nm":"Sweet Gum"}
],
"total_pollen_cnt":1156,
"stn_cmnt_cd":"H",
"stn_cmnt":"Operating Normally",
"pollenobservation":[
{"pollen_type":"Tree","pollen_idx":"4","pollen_desc":"Very High"},
{"pollen_type":"Grass","pollen_idx":"0","pollen_desc":"None"},
{"pollen_type":"Weed","pollen_idx":"0","pollen_desc":"None"},
{"pollen_type":"Mold","pollen_idx":"9","pollen_desc":"No Data"}
]}]}

```

#### URL Path Components
|**URL Part**|**URL Part Type**|**Description**|
| :- | :- | :-: |
|hostname|host|**api.weather.com** is the host for these API’s|
|version|Path Part|Current API version (example:  "v1","v2")|
|geocode|Query Parameter|For API’s which require a location for the data, i.e., latitude and longitude (ex. 34.53,-84.50)|
|language|Query Parameter|Language to return the response in (ex. en-US)|
|format|Quaery Parameter|The format of the response (“json”)|
|apikey|Query Parameter|API key for accessing the API|

#### Data Elements & Descriptions
|**Field Name**|**Description**|**Data Type**|**Null**|**Range**|**Sample**|
| :- | :- | :- | :- | :- | :-: |
|**Metadata**||||||
|Version|API version number|String|N||1|
|transaction_id|Generated transaction id for the API call|String|N||7506556217027201134|
|expire_time_gmt|Data expiration date/ time in UNIX seconds |Long|N|Unlimited|1373914800|
|**US Pollen Observations**||||||
|class|Type of data|String|N|pollenobs|pollenobs|
|loc_id|Pollen station id|String|N|any valid pollen station|ALT|
|loc_nm|City name|String|N||Atlanta|
|loc_st|State name|String|N||GA|
|rpt_dt|The date and time the pollen observation was reported|Date|N|YYYY-MM-DD'T'HH:MM:SSZ|2014-04-08T15:00:00Z|
|process time gmt|processed date/time in UNIX seconds|Long|N|Unlimited|1367892140|
|**Tree Name – occurs 3 times**||||||
|tree_nm|The name of the tree species with the highest observed pollen count|String|N|![](https://github.com/abinash589/demo/blob/main/Tree%20Name.PNG) |Cedar|