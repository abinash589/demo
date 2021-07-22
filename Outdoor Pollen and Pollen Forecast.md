# Outdoor Pollen and Pollen Forecast
- There are 2 process for pollen data. They are:
  - Pollen Outdoor Process
  - Pollen Forecast Process

## Pollen Outdoor Process
- This process uses an IBM API, **US Pollen Observation**, to get the pollen data and not pollutants data(PM2.5,PM10,PM1).
- The US Pollen Observation API returns the pollen observation content for a valid latitude/longitude coordinate, for the current date.
- The API will return the index and index description for four pollen types- tree pollen, grass pollen, weed pollen, mold pollen.
- The API supports two languages – English and Spanish for the US.
- Pollen data provided through this API is sourced from trusted third-party organization that collects data from allergist’s offices on weekdays, Monday – Friday, except holidays.
- There are four segments of the data feed. The first contains the metadata, which includes the specified language parameter in the request URL.
- The remaining data segments contain information on the location, reporting date/time and station, the specific tree species, and index for tree pollen, grass pollen, weed pollen, or mold pollen.
- **API URl:** '''https://api.weather.com/v1/geocode/'''+ str(lat) + """/""" + str(long) +'''/observations/pollen.json?language=en-US&apiKey=''' + apiKey
  - Required Parameters: geocode,language, format,apikey
- **JSON Response:**
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
|process time gmt|Processed date/time in UNIX seconds|Long|N|Unlimited|1367892140|
|**Tree Name – occurs 3 times**||||||
|tree_nm|The name of the tree species with the highest observed pollen count|String|N|![](https://github.com/abinash589/demo/blob/main/Tree%20Name.PNG) |Cedar|
|total_pollen_cnt|The total observed pollen count of the specified plants being measured at the location|Integers|Y|grains per cubic meter|551 grains per cubic meter|
|stn_cmnt_cd|The pollen station comment code|String|Y|A - No Report, B - Equipment Failure, C - Reports only during weed pollen season, D - Reports Suspended, E - Rain/Inclement Weather, F - Does not report year round, G - Report valid more than one day, H- Operating Normally|H|
|stn_cmnt|The reporting status of the pollen status|String|Y|No Report, Equipment Failure, Reports only during weed pollen season, Operating Normally, etc|operating normally|
|**Pollen Observation – Occurs 4 times – Tree, Grass, Weed and Mold**||||||
|pollen_type|Type of pollen|String|N|![Pollen Types](https://github.com/abinash589/demo/blob/main/Pollen%20Types.PNG) |Tree|
|pollen_idx|Pollen index value|String|N|0 to 4 or 9|1|
|pollen_desc|Pollen index description|String|N|![Pollen Index Description](https://github.com/abinash589/demo/blob/main/Pollen%20Index%20Description.PNG) |1|

#### Pollen Outdoor Process Flowchart
![Outdoor Pollen Process](https://github.com/abinash589/demo/blob/main/Outdoor%20Pollen%20Process.PNG)

## Pollen Forecast Process 
- This process uses an IBM API, **Forecast Indices API**, that provides forecast data.
- The Forecast Indices API will return the data for coming future days(3,5,7,10 or 15 days).
- The Pollen index provides forecast indices for Grass, Ragweed, and Tree pollen.
- **API URL:** https://api.weather.com/v2/indices/pollen/daypart/15day?geocode=latitude,longitude&language=en-US&format=json&apiKey=yourAPIKey
- **JSON Response:**
```javascript
{"metadata": {},
"pollenForecast12hour": {
"fcstValid": [],
"fcstValidLocal": [],
"dayInd": [],
"num": [],
"daypartName": [],
"grassPollenIndex": [],
"grassPollenCategory": [],
"treePollenIndex": [],
"treePollenCategory": [],
"ragweedPollenIndex": [],
"ragweedPollenCategory": []
}}

```
#### URL Path Components
|**URL Part**|**URL Part Type**|**Description**|
| :- | :- | :-: |
|hostname|host|**api.weather.com** is the host for these API’s|
|version|Path Part|Current API version (example: "v2")|
|geocode|Query Parameter|For API’s which require a location for the data, i.e., latitude and longitude (ex. 34.53,-84.50)|
|language|Query Parameter|Language to return the response in (ex. en-US)|
|format|Quaery Parameter|The format of the response (“json”)|
|apikey|Query Parameter|API key for accessing the API|

#### Data Elements & Descriptions
|**Field Name**|**Description**|**Data Type**|**Null**|**Range**|**Sample**|
| :- | :- | :- | :- | :- | :-: |
|fcstValid|Time forecast is valid ... start of the forecast period, always 7am local time.|String|N||1369306800|
|fcstValidLocal|Time forecast is valid ... start of the forecast period, always 7am local time.|Date|N||2013-05-23T07:00:00-0400|
|num|Daypart Segment (12hour) - Sequential daypart number, where 1 = daytime of Day 0|Integer|N||21|
|dayInd|Day / Night Indicator|String|N|D,N|D|
|daypartName|Name of 12hr daypart, not including day names in first 48hrs|String|N||Tomorrow|
|**Pollen Index**||||||
|grassPollenCategory|Descriptive text of Grass Pollen Index|String|N||Low|
|grassPollenIndex|Forecast Grass Pollen Index. 0=none / out of season, 1=low, 2=moderate, 3=high, 4=very high|Integer|N|0,4|2|
|ragweedPollenCategory|Descriptive text of Ragweed Pollen Index|String|N||Low|
|ragweedPollenIndex|Forecast Ragweed Pollen Index. 0=none / out of season, 1=low, 2=moderate, 3=high, 4=very high|Integer|N|0,4|1|
|treePollenCategory|Descriptive text of Tree Pollen Index|String|N||Low|
|treePollenIndex|Forecast Grass Pollen Index. 0=none / out of season, 1=low, 2=moderate, 3=high, 4=very high|Integer|N|0,4|3|

#### Pollen Forecast Process Flowchart
![](https://github.com/abinash589/demo/blob/main/Pollen%20Forecast%20Process.PNG)



## API Call Frequency
|**API Name**|**Frequency**|**Purpose**|
| :- | :- | :-: |
|US Pollen Observation|Once in a day|Return the index and index description for different types of pollen, for a valid latitude/longitude.|
|Forecast Indices|Once in a day|Return the forecast indices for grass, ragweed and tree pollen, for coming future days|