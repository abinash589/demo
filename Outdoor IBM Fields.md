### WeatherAPI Outdoor IBM- Pollutant Values

- This API includes an overall Air Quality Index, Air Quality Category Index, category, principal pollutant type, measurement, index number and level, and any applicable health recommendation text.
- **API URL**: '''https://api.weather.com/v3/aggcommon/v3-wx-globalAirQuality?geocodes='''+geostring+''';&language=en-US&scale=EPA&format=json&apiKey='''+apiKey
	- Geostring is comma separated co-ordinates (latitude,longitude) followed by semicolon ;
- JSON Response:
```javascript
//This response is for 1 lat/long

"globalairquality": {
       "latitude": 44.798,
       "longitude": -63.102,
       "source": "Powered by Copernicus Atmosphere Monitoring Service",
       "disclaimer": "Neither the European Commission nor ECMWF is responsible for any use of this information",
       "airQualityIndex":101,
       "airQualityCategory": "Unhealthy for Sensitive Groups",
       "airQualityCategoryIndex": 3,
       "airQualityCategoryIndexColor": "039963",
       "primaryPollutant": "PM2.5",
       "pollutants": {
           "NO2": {
               "name": "NO2",
               "phrase": "Nitrogen Dioxide",
               "amount": 41.4,
               "unit": "ug/m3",
               "category": "Good",
               "categoryIndex": 1,
               "index": 21
           },
           "O3": {
               "name": "O3",
               "phrase": "Ozone",
               "amount": 110.0,
               "unit": "ug/m3",
               "category": "Good",
               "categoryIndex": 1,
               "index": 50
           },
           "SO2": {
               "name": "SO2",
               "phrase": "Sulfur Dioxide",
               "amount": 26.2,
               "unit": "ug/m3",
               "category": "Good",
               "categoryIndex": 1,
               "index": 14
           },
           "PM2.5": {
               "name": "PM2.5",
               "phrase": "Particulate matter less than 2.5 microns",
               "amount": 35,
               "unit": "ug/m3",
               "category": "Unhealthy for Sensitive Groups",
               "categoryIndex": 3,
               "index": 101
           },
           "PM10": {
               "name": "PM10",
               "phrase": "Particulate matter less than 10 microns",
               "amount": 154.5,
               "unit": "ug/m3",
               "category": "Moderate",
               "categoryIndex": 2,
               "index": 100
           },
           "CO": {
               "name": "CO",
               "phrase": "Carbon Monoxide",
               "amount": 8020.3,
               "unit": "ug/m3",
               "category": "Moderate",
               "categoryIndex": 2,
               "index": 76
           }
       },
       "messages": {
           "Sensitive Group": {
               "title": "Sensitive Groups",
               "text": "Reduce prolonged or heavy exertion. It's OK to be active outside, but take more breaks and do less intense activities. Watch for symptoms such as coughing or shortness of breath."
           },
           "General": {
               "title": "General",
               "text": "Members of sensitive groups may experience health effects. The general public is not likely to be affected."
           }
       },
       "expireTimeGmt":1625544000
   }
}
```
  
#### Field Names & Definitions
|**Field Name**|**Description**|**Type**|**Range**|**Sample**|**Nulls Allowed**|
| :- | :- | :-: | :- | :- | :-: |
|**globalairquality**|**Response Section Header: Non-Repeating Elements**|**object**||||
|latitude|Latitude|decimal|N/A|<p>44.798</p><p>Note - truncated to 2-digit decimal by default</p>|N|
|longitude|Longitude|decimal|N/A|<p>-63.102</p><p>Note - truncated to 2-digit decimal by default</p>|N|
|source|Data must be attributed as: "Powered by <source>[year]"|string|Powered by Copernicus Atmosphere Monitoring Service Information [Year]|Powered by Copernicus Atmosphere Monitoring Service Information [2018]|N|
|disclaimer|Neither the European Commission nor ECMWF is responsible for any use of this information.|string|Neither the European Commission nor ECMWF (European Centre for Medium-Range Weather Forecasts) is responsible for any use of this information.|Neither the European Commission nor ECMWF is responsible for any use of this information.|N|
|airQualityIndex|Air quality index|decimal|0 to unbounded |61|N|
|airQualityCategory|Air quality category|string|<p>Good, Moderate, </p><p>Unhealthy for Sensitive Groups,</p><p>Unhealthy, Very Unhealthy, Hazardous</p>|Moderate|N|
|airQualityCategoryIndex|Index summarizing the air quality categories|integer|1,2,3,4,5,6|2|N|
|airQualityCategoryIndexColor|Air Quality Category Index Scale to Color|string|<p>00E838, FFFF24, FF7200,</p><p>FF0000,9D3D8C,8D0021</p>|#90D32D|N|
|primaryPollutant|Indicates primary pollutant|string|<p>O3 = Ozone</p><p>CO: Carbon Monoxide</p><p>NO2: Nitrogen Dioxide</p><p>SO2: Sulphur Dioxide</p><p>PM2.5: Particulate matter less than 2.5 microns</p><p>PM10: Particulate matter less than 10 microns</p>|PM2.5|N|
|expireTimeGmt|Expiration time in UNIX seconds|epoch||1369252800|N|
|**messages**|**messages**|**object**||||
|title|Named message type|string|<p>General, Sensitive Groups</p><p></p>|General|N|
|text|Message verbiage|string||Members of sensitive groups may experience health effects. The general public is not likely to be affected.|N|
|**pollutants**|**pollutants**|**object**||||
|name|Pollutant name|string|<p>O3</p><p>CO</p><p>NO2</p><p>SO2</p><p>PM2.5</p><p>PM10</p>|PM2.5|N|
|phrase|Pollutant description|string|Ozone, Carbon Monoxide, Nitrogen Dioxide, Sulphur Dioxide, Particulate matter less than 2.5 microns, Particulate matter less than 10 microns|Ozone|N|
|amount|Measure of concentration of pollutant.|decimal||485.25|N|
|unit|Pollutant Unit|string|ug/m3|µg/m3|N|
|category|Pollutant Category|string|<p>Good, Moderate, </p><p>Unhealthy for Sensitive Groups,</p><p>Unhealthy, Very Unhealthy, Hazardous</p>|Moderate|N|
|categoryIndex|Pollutant Category Index|decimal|1,2,3,4,5,6|2|N|
|index|Pollutant index|decimal|Positive Integer|22|N|



### HistoricAPI Outdoor IBM- Temperature and Humidity

- The API provides information on temperature, precipitation, wind, barometric pressure, visibility, ultraviolet (UV) radiation, and other related weather observations elements as well as date/time, weather icon codes and phrases.
- The field names are sorted alphabetically in the table below. It doesn't represent the sort order of the API response.
- Each field in the response contains 24 values for 24 hours, for each lat/long.
- **API URL**: '''https://api.weather.com/v3/aggcommon/v3-wx-conditions-historical-hourly-1day?geocodes='''+geostring+'''&language=en-US&format=json&units=m&apiKey='''+apiKey
	- Geostring is comma separated co-ordinates (latitude,longitude) followed by semicolon ; 
- JSON Response:
```javascript
//This response is for 1 lat/long

[
    {
        "id": "44.798,-63.102",
        "v3-wx-conditions-historical-hourly-1day": {
                    “cloudCeiling”:[1200...],
                    "dayOfWeek": ["Saturday",...],
                    "dayOrNight": ["D",...],
                    "expirationTimeUtc": [1474132031,...],
                    "iconCode": [30,...],
                    "iconCodeExtend": [3000,...],
                    "precip24Hour": [0,...],
                    "pressureAltimeter": [30.14,...],
                    "pressureChange": [-0.05,...],
                    "pressureMeanSeaLevel": [1020.6,...],
                    "pressureTendencyCode": [2,...],
                    "pressureTendencyTrend": ["Falling",...],
                    "relativeHumidity": [51,...],
                    "snow24Hour": [0,...],
                    "sunriseTimeLocal": ["2016-09-17T07:21:26-0400",...],
                    "sunriseTimeUtc": [1474111286,...],
                    "sunsetTimeLocal": ["2016-09-17T19:39:03-0400",...],
                    "sunsetTimeUtc": [1474155543,...],
                    "temperature": [86,...],
                    "temperatureChange24Hour": [-2,...],
                    "temperatureDewPoint": [66,...],
                    "temperatureFeelsLike": [89,...],
                    "temperatureHeatIndex": [89,...],
                    "temperatureMax24Hour": [90,...],
                    "temperatureMaxSince7Am": [86,...],
                    "temperatureMin24Hour": [67,...],
                    "temperatureWindChill": [86,...],
                    "uvDescription": ["High",...],
                    "uvIndex": [7,...],
                    "validTimeLocal": ["2016-09-17T12:45:00-0400",...],
                    "validTimeUtc": [1474130700,...],
                    "visibility": [10,...],
                    "windDirection": [110,...],
                    "windDirectionCardinal": ["ESE",...],
                    "windGust": [null,...],
                    "windSpeed": [9,...],
                    "wxPhraseLong": ["Partly Cloudy",...]
    }
]

```

#### Field Names & Definitions
|Field Name|Description|Type|Range|Sample|Nulls Allowed|
| :- | :- | :-: | :- | :- | :-: |
|cloudCeiling|Base of lowest Mostly Cloudy or Cloudy layer. Note: This field can be NULL for any geographic location depending weather conditions|[integer]|Base of lowest Mostly Cloudy or Cloudy layer<br>Note: This field can be NULL for any geographic location depending weather conditions|1200|Y|
|dayOfWeek|Day of week|[string]|Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday|Thursday|Y|
|dayOrNight|Daytime or night-time of the local apparent time of the location|[string]|D = Day, N = Night, X = Missing (for extreme northern and southern hemisphere|D|Y|
|expirationTimeUtc|Expiration time in UNIX in UNIX epoch value|[epoch]|-|1369252800|Y|
|iconCode|This number is the key to the weather icon lookup. The data field shows the icon number that is matched to represent the observed weather conditions.|[integer]|0 to 47|30|Y|
|iconCodeExtend|<p>A four-digit code representing the full set of sensible weather icons.  These codes are companions to iconCode with more specificity.</p><p>**Note**: Reserved for internal purposes only.</p>|[integer]|-|3200|Y|
|precip24Hour|<p>Liquid precip amount in the last 24 hours.</p><p>**Note:** Arrival of new, refined data inputs may cause output values to change throughout a given day</p>|[decimal]|-|0|Y|
|pressureAltimeter|Barometric pressure is the pressure exerted by the atmosphere at the Earth’s surface due to the weight of the air. Expressed in inches of mercury when units=a (i.e. units='US'), expressed in millibars when units=Metric, Hybrid or Metric\_SI|[decimal]|<p>Inches of mercury, precise to hundredths…</p><p>Precision to tenths when in millibars</p>|30.18|Y|
|pressureChange|Change in pressure in the last three hours (inches of mercury for units=US, millibars otherwise) |[decimal]|-|-0.03|Y|
|pressureMeanSeaLevel|Mean sea level pressure in millibars|[decimal]|Millibars, precise to 1/10th mb|1022.4|Y|
|pressureTendencyCode|Code of pressure tendency. 0 = steady, 1 = rising, 2 = falling, 3 = rising rapidly, 4 = falling rapidly|[integer]|0 - 4|0|Y|
|pressureTendencyTrend|Descriptive text of pressure tendency over the past three hours. |[string]|Steady, Rising, Rapidly Rising, Falling, Rapidly Falling|Steady|Y|
|relativeHumidity|The relative humidity of the air, which is defined as the ratio of the amount of water vapor in the air to the amount of vapor required to bring the air to saturation at a constant temperature. Relative humidity is always expressed as a percentage.|[integer]|0 to 100|55|Y|
|snow24Hour|<p>Snowfall amount in the last 24 hours.</p><p>**Note:** Arrival of new, refined data inputs may cause output values to change throughout a given day</p>|[decimal]|-|0|Y|
|sunriseTimeLocal|This field contains the local time of the sunrise. It reflects any local daylight savings conventions. For a few Arctic and Antarctic regions, the Sunrise and Sunset data values may be the same (each with a value of 12:01am) to reflect conditions where a sunrise or sunset does not occur.|[ISO]|YYYY-MM-DDTHH:MM:SS-NNNN; NNNN=GMT offset|2014-08-20T10:47:59-0500|Y|
|sunriseTimeUtc|Sunrise time in UNIX epoch value|[epoch]|-|1369252800|Y|
|sunsetTimeLocal|<p>This field contains the local time of the sunset. It reflects any local daylight savings conventions.</p><p>For a few Arctic and Antarctic regions, the Sunrise and Sunset data values may be the same (each with a value of 12:01am) to reflect conditions where a sunrise or sunset does not occur.</p>|[ISO]|YYYY-MM-DDTHH:MM:SS-NNNN; NNNN=GMT offset|2014-08-20T10:47:59-0500|Y|
|sunsetTimeUtc|Sunset time in UNIX epoch value |[epoch]|-|1369252800|Y|
|temperature|Temperature in defined unit of measure|[integer]|-140 to 140|74|Y|
|temperatureChange24Hour|Change in temperature compared to the report 24 hours ago.|[integer]|-|-26|Y|
|temperatureDewPoint|The temperature which air must be cooled at constant pressure to reach saturation. The Dew Point is also an indirect measure of the humidity of the air. The Dew Point will never exceed the Temperature. When the Dew Point and Temperature are equal, clouds or fog will typically form. The closer the values of Temperature and Dew Point, the higher the relative humidity.|[integer]|<p>-80 to 100 (°F) or</p><p>-62 to 37 (°C)</p>|60|Y|
|temperatureFeelsLike|<p>An apparent temperature. It represents what the air temperature “feels like” on exposed human skin due to the combined effect of the wind chill or heat index.</p><p>When the temperature is 65°F or higher, the Feels Like value represents the computed Heat Index.  When the temperature is below 65°F, the Feels Like value represents the computed Wind Chill.</p><p>Units - Expressed in fahrenheit when units=e, expressed in celsius when units=m, s, or h.</p><p>Range - -140 to 140</p>|[integer]|-140 to 140|101|Y|
|temperatureHeatIndex|<p>An apparent temperature.  It represents what the air temperature “feels like” on exposed human skin due to the combined effect of warm temperatures and high humidity.</p><p>Below 65°F, it is set = to the temperature. </p><p>Units - Expressed in fahrenheit when units=e, expressed in celsius when units=m, s, or h.</p>|[integer]|-|98|Y|
|temperatureMax24Hour|Max temperature in the last 24 hours |[integer]|-|65|Y|
|temperatureMaxSince7Am|Max temperature since 7 A.M. |[integer]|-|65|Y|
|temperatureMin24Hour|Min temperature in the last 24 hours|[integer]|-|65|Y|
|temperatureWindChill|<p>An apparent temperature. It represents what the air temperature “feels like” on exposed human skin due to the combined effect of the cold temperatures and wind speed. </p><p>Above 65°F, it is set = to the temperature. </p><p>Units - Expressed in fahrenheit when units=e, expressed in celsius when units=m, s, or h</p>|[integer]|-|-34|Y|
|uvDescription|The UV Index Description which complements the UV Index value by providing an associated level of risk of skin damage due to exposure. -2 = Not Available, -1 = No Report, 0 to 2 = Low, 3 to 5 = Moderate, 6 to 7 = High, 8 to 10 = Very High, 11 to 16 = Extreme|[string]|Not Available, No Report, Low, Moderate, High, Very High, Extreme|Low|Y|
|uvIndex|TWC-created UV index|[integer]|0 to 11|6|Y|
|validTimeLocal|Time observation is valid in local, but at top of next UTC hour|[ISO]|YYYY-MM-DDTHH:MM:SS-NNNN; NNNN=GMT offset|2014-08-20T10:47:59-0500|Y|
|validTimeUtc|Time observation is valid in UNIX epoch value |[epoch]|-|1369252800|Y|
|visibility|The horizontal visibility at the observation point. Visibilities can be reported as fractional values particularly when visibility is less than 2 miles. Visibilities greater than 10 statute miles (16.1 kilometres) which are considered “unlimited” are reported as “999” in your feed. You can also find visibility values that equal zero. This occurrence is not wrong. Dense fogs and heavy snows can produce values near zero. Fog, smoke, heavy rain and other weather phenomena can reduce visibility to near zero miles or kilometres.|[decimal]|<p>0 to 999 or null;</p><p>For greater than 1 = one decimal.</p><p>For less than 1 = 2 (Metric) & 2 (Imperial) decimal places.</p>|10.2|Y|
|windDirection|The direction from which the wind blows expressed in degrees. The magnetic direction varies from 0 to 359 degrees, where 0° indicates the North, 90° the East, 180° the South, 270° the West, and so forth.|[integer]|0<=wind\_dire\_deg<=350, in 10 degree interval|60|Y|
|windDirectionCardinal|This field contains the cardinal direction from which the wind blows in an abbreviated form. Wind directions are always expressed as “from whence the wind blows” meaning that a North wind blows from North to South. If you face North in a North wind, the wind is at your face. Face southward and the North wind is at your back.|[string]|N, NNE, NE, ENE, E, ESE, SE, SSE, S, SSW, SW, WSW, W, WNW, NW, NNW, CALM|ENE|Y|
|windGust|This data field contains information about sudden and temporary variations of the average Wind Speed. The report always shows the maximum wind gust speed recorded during the observation period. It is a required display field if Wind Speed is shown. The speed of the gust can be expressed in miles per hour or kilometres per hour.|[integer]|-|28|Y|
|windSpeed|The wind is treated as a vector; hence, winds must have direction and magnitude (speed). The wind information reported in the hourly current conditions corresponds to a 10-minute average called the sustained wind speed. Sudden or brief variations in the wind speed are known as “wind gusts” and are reported in a separate data field. Wind directions are always expressed as "from whence the wind blows" meaning that a North wind blows from North to South. If you face North in a North wind the wind is at your face. Face southward and the North wind is at your back.|[integer]||8|Y|
|wxPhraseLong|A text description of the observed weather conditions at the location|[string]||Partly Cloudy|Y|

