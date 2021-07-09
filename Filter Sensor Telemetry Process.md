## Filter Sensor Process
### Flowchart:
![](https://github.com/abinash589/demo/blob/main/FilterSensorFlowchart.PNG)

### JSON Message:
```javascript
{
"filterId" : "20225",
"batteryLife" : 100,
"batteryLifeTS" : "2021-07-08T23:03:18.000Z"
"org_batteryLifeTS" : "2021-07-08T23:03:18Z"
    "sensorDataList" : [{
        "sensorData" : {
        "UnixTS" : 1.62577955E9,
        "Temperature" :  35.50,
        "Pressure" : 123.45 ,
        }
    }]
}
```

### Field Names & Definitions:
|**Field Name**|**Description**|**Type**|**Sample**|
| :- | :- | :-: | :- |
|filterId|A primary key field that would be created automatically every time a new filter is inserted|int|eg: 20225|
|batteryLife|Health of a battery|int|eg: 0 to 100|
|batteryLifeTS|This field contains timestamp of battery life|datetime|YYYY-MM-DDThh:mm:ss.sssZ|
|org_batteryLifeTS|This field contains timestamp of battery life|datetime|YYYY-MM-DDThh:mm:ssZ|
|UnixTS|Sensor data time in Unix epoch value(in seconds)|bigint|eg: 1.62577955E9|
|Temperature|Temperature in defined unit of measure(in Celsius)|double|eg: 37.67°C|
|Pressure|Pressure in defined unit of measure(in  µg/m^3)|double|eg: 156.49  µg/m3|
