***MixPanel API and events***

***Following are the mixpanel API call information for getting the
response***

  URL                https://data.mixpanel.com/api/2.0/export   
  ------------------ ------------------------------------------ ------------------
  Input Parameters   from\_date                                 yyyy-mm-dd
                     to\_date                                   yyyy-mm-dd
                     Event                                      \["Event Name"\]
  Response           JSON                                       

Following are the Event Name to be passed in Mixpanel API for getting
the responses

  **Event**                                **Description**
  ---------------------------------------- -------------------------------------------
  Accept user agreement                     
  Alert opened                              
  Amazon one time                           
  App open                                  
  Brightness                                
  Buy replacement                           
  Call support on error                     
  Change email                              
  Change email incomplete                   
  Change password                           
  Coming soon learn more                    
  Data gap with access to location          
  Data gap with no access to location       
  Delete Filter                             Give the responses on the filter deleted
  Delete property                           
  Device created                            
  Device not listed                         
  Device offline                            Give the responses on the offline device
  Device offline troubleshoot               
  Device removed                            Give the responses on the removed device
  DRS error                                 
  DRS sign up begin                         
  DRS teaser seen                           
  Edit profile                              
  Email Validated                           
  Fan speed                                 
  FAQs opened                               
  FFS property flow canceled                
  FFS property flow completed               
  FFS property flow started                 
  Filter added                              
  Filter pairing canceled                   
  Filter selected                           
  Filter type selected                      
  First Log in                              
  Found RAP model                           
  Geofence created                          
  Graph opened                              
  Graph page view                           
  Graph tab view                            
  Graph view duration                       
  Help                                      
  Info page reading time                    
  Learn more page is opened                 
  Learn more question opened                
  Location error                            
  Location not found                        
  Location not right now alert              
  Location permission set                   
  Location permission skipped               
  Log in                                    
  Log out                                   
  Missing product image                     
  My air location soft ask                  
  Network connection                        
  Network selected                          
  Networks available                        
  New device                                
  Notification permission                   
  Only while using permission update        
  Outdoor added                             
  Outdoor deleted                           
  Pairing with sensor                       
  Pollutant Selected                        
  Pollutant selected                        
  Power mode                                
  Pressed buy                               
  Problematic UPC found                     
  Product family                            
  Property created                          
  Property flow cancelled                   
  Property naming                           
  Provisioning call support                 
  Provisioning error                        
  Provisioning flow BLE connecting          
  Provisioning flow BLE searching           
  Provisioning flow canceled                
  Provisioning flow started                 
  Provisioning help needed                  
  Pull to refresh                           
  Pull to refresh sensor connection         
  Pull to refresh toasts                    
  Push notification opened                  
  Push notification soft ask                
  Rename property                           
  Replaced filter                           
  Replaced with Smart filter                
  Replacement instructions                  
  Resend                                    
  Retailer selected                         
  Room already exists                       
  Room name changed                         
  Room naming                               
  Screen home indoor select                 
  Screen view                               
  Search for address                        
  Searching for sensor                      
  Sensor data collection info               
  Sensor data received with sample          
  Sensor found                              
  Sensor powercycled                        
  Sensor throttling                         
  Shortcut added                            
  Sign up                                   
  Size selected                             
  Smart filter pairing location soft ask    
  Smart filter pairing start                
  Smart filter scanned                      
  SRAP provisioning location soft ask       
  Start scanning                            
  Tapping x                                 
  Timer                                     
  Tip opened                                
  Widget activation                         
  Widget added                              
  Widget uninstall                          
  Works with finished                       
  Works with opened                         
  Works with started                        

Sample Input parameters and responses from the Mixpanel are given below

  ----------------------------------------------------------------------------------------------------------
  URL                https://data.mixpanel.com/api/2.0/export                  
  ------------------ --------------------------------------------------------- -----------------------------
  Input Parameters   from\_date                                                2020-12-29

                     to\_date                                                  2020-12-31

                     Event                                                     \["Accept user agreement"\]

  Response           {
                     
                     "event": "Accept user agreement",
                     
                     "properties": {
                     
                     "time": 1609420266,
                     
                     "distinct\_id": "849DBA18-C0AB-4A49-9A23-B5434834A238",
                     
                     "\$app\_build\_number": "1.12.0.4522",
                     
                     "\$app\_version\_string": "1.12.0",
                     
                     "\$carrier": "Verizon",
                     
                     "\$city": "Meridian",
                     
                     "\$device\_id": "849DBA18-C0AB-4A49-9A23-B5434834A238",
                     
                     "\$insert\_id": "f9c260a69955289f",
                     
                     "\$lib\_version": "2.7.7",
                     
                     "\$manufacturer": "Apple",
                     
                     "\$model": "iPhone10,3",
                     
                     "\$os": "iOS",
                     
                     "\$os\_version": "14.2",
                     
                     "\$radio": "LTE",
                     
                     "\$region": "Idaho",
                     
                     "\$screen\_height": 812,
                     
                     "\$screen\_width": 375,
                     
                     "\$wifi": true,
                     
                     "Status": "accept",
                     
                     "mp\_country\_code": "US",
                     
                     "mp\_lib": "swift",
                     
                     "mp\_processing\_time\_ms": 1609449079378
                     
                     }
                     
                     }
  ----------------------------------------------------------------------------------------------------------

  -------------------------------------------------------------------------------------------------
  URL                https://data.mixpanel.com/api/2.0/export                  
  ------------------ --------------------------------------------------------- --------------------
  Input Parameters   from\_date                                                2020-12-29

                     to\_date                                                  2020-12-31

                     Event                                                     \["Alert opened"\]

  Response           {
                     
                     "event": "Alert opened",
                     
                     "properties": {
                     
                     "time": 1609274085,
                     
                     "distinct\_id": "16D83774-01E3-46AD-AD1D-2C73AB954D8A",
                     
                     "\$app\_build\_number": "1.12.0.4522",
                     
                     "\$app\_version\_string": "1.12.0",
                     
                     "\$carrier": "Verizon",
                     
                     "\$city": "Sacramento",
                     
                     "\$device\_id": "16D83774-01E3-46AD-AD1D-2C73AB954D8A",
                     
                     "\$insert\_id": "0876380100eb01b4",
                     
                     "\$lib\_version": "2.7.7",
                     
                     "\$manufacturer": "Apple",
                     
                     "\$model": "iPhone10,2",
                     
                     "\$os": "iOS",
                     
                     "\$os\_version": "14.2",
                     
                     "\$radio": "LTE",
                     
                     "\$region": "California",
                     
                     "\$screen\_height": 736,
                     
                     "\$screen\_width": 414,
                     
                     "\$wifi": true,
                     
                     "AlertID": "1587073",
                     
                     "DeviceID": "469263",
                     
                     "Screen deep-linked": "filter",
                     
                     "User email": "ujph1010@yahoo.com",
                     
                     "mp\_country\_code": "US",
                     
                     "mp\_lib": "swift",
                     
                     "mp\_processing\_time\_ms": 1609302925509
                     
                     }
                     
                     }
  -------------------------------------------------------------------------------------------------

  ----------------------------------------------------------------------------------------------------
  URL                https://data.mixpanel.com/api/2.0/export                  
  ------------------ --------------------------------------------------------- -----------------------
  Input Parameters   from\_date                                                2020-12-29

                     to\_date                                                  2020-12-31

                     Event                                                     \["Amazon one time"\]

  Response           {
                     
                     "event": "Amazon one time",
                     
                     "properties": {
                     
                     "time": 1609399132,
                     
                     "distinct\_id": "4088C1FA-6088-41D6-A1FD-0D17E349030A",
                     
                     "\$app\_build\_number": "1.11.4319",
                     
                     "\$app\_version\_string": "1.11",
                     
                     "\$carrier": "T-Mobile",
                     
                     "\$city": "Lansdowne",
                     
                     "\$device\_id": "4088C1FA-6088-41D6-A1FD-0D17E349030A",
                     
                     "\$had\_persisted\_distinct\_id": false,
                     
                     "\$insert\_id": "f5450ddbd02af2cd",
                     
                     "\$lib\_version": "2.7.7",
                     
                     "\$manufacturer": "Apple",
                     
                     "\$model": "iPhone11,2",
                     
                     "\$os": "iOS",
                     
                     "\$os\_version": "14.2",
                     
                     "\$radio": "LTE",
                     
                     "\$region": "Pennsylvania",
                     
                     "\$screen\_height": 812,
                     
                     "\$screen\_width": 375,
                     
                     "\$wifi": false,
                     
                     "User email": "ivanoksan@yahoo.com",
                     
                     "mp\_country\_code": "US",
                     
                     "mp\_lib": "swift",
                     
                     "mp\_processing\_time\_ms": 1609427961445
                     
                     }
                     
                     }
  ----------------------------------------------------------------------------------------------------

  ---------------------------------------------------------------------------------------------
  URL                https://data.mixpanel.com/api/2.0/export                  
  ------------------ --------------------------------------------------------- ----------------
  Input Parameters   from\_date                                                2020-12-29

                     to\_date                                                  2020-12-31

                     Event                                                     \["App open"\]

  Response           {
                     
                     "event": "App open",
                     
                     "properties": {
                     
                     "time": 1609369820,
                     
                     "distinct\_id": "EBCD024A-3970-4915-A719-82DF68DADAA4",
                     
                     "\$app\_build\_number": "1.10.3976",
                     
                     "\$app\_version\_string": "1.10",
                     
                     "\$carrier": "AT&T",
                     
                     "\$city": "Los Angeles",
                     
                     "\$device\_id": "EBCD024A-3970-4915-A719-82DF68DADAA4",
                     
                     "\$had\_persisted\_distinct\_id": true,
                     
                     "\$insert\_id": "fcdeec64e9999fde",
                     
                     "\$lib\_version": "2.7.7",
                     
                     "\$manufacturer": "Apple",
                     
                     "\$model": "iPhone9,4",
                     
                     "\$os": "iOS",
                     
                     "\$os\_version": "14.3",
                     
                     "\$radio": "LTE",
                     
                     "\$region": "California",
                     
                     "\$screen\_height": 736,
                     
                     "\$screen\_width": 414,
                     
                     "\$wifi": false,
                     
                     "App status": "cold start",
                     
                     "Bluetooth on": false,
                     
                     "Location permission": false,
                     
                     "Notification permission status": "Granted",
                     
                     "mp\_country\_code": "US",
                     
                     "mp\_lib": "swift",
                     
                     "mp\_processing\_time\_ms": 1609398639199
                     
                     }
                     
                     }
  ---------------------------------------------------------------------------------------------

  ---------------------------------------------------------------------------------------------------
  URL                https://data.mixpanel.com/api/2.0/export                  
  ------------------ --------------------------------------------------------- ----------------------
  Input Parameters   from\_date                                                2020-12-29

                     to\_date                                                  2020-12-31

                     Event                                                     \["Device offline"\]

  Response           {
                     
                     "event": "Device offline",
                     
                     "properties": {
                     
                     "time": 1609348133,
                     
                     "distinct\_id": "225CC746-85BE-40CF-A9CC-46A94E0D6AF2",
                     
                     "\$app\_build\_number": "1.12.0.4522",
                     
                     "\$app\_version\_string": "1.12.0",
                     
                     "\$carrier": "T-Mobile",
                     
                     "\$city": "Las Vegas",
                     
                     "\$device\_id": "48B5E9E3-D353-47CC-937B-343420B6B9C1",
                     
                     "\$distinct\_id\_before\_identity": "324172",
                     
                     "\$insert\_id": "4b9d04bb1df5dfb8",
                     
                     "\$lib\_version": "2.7.7",
                     
                     "\$manufacturer": "Apple",
                     
                     "\$model": "iPhone13,4",
                     
                     "\$os": "iOS",
                     
                     "\$os\_version": "14.3",
                     
                     "\$radio": "NRNSA",
                     
                     "\$region": "Nevada",
                     
                     "\$screen\_height": 812,
                     
                     "\$screen\_width": 375,
                     
                     "\$user\_id": "324172",
                     
                     "\$wifi": true,
                     
                     "Device type": "Purpleair",
                     
                     "User email": "billm56@aol.com",
                     
                     "mp\_country\_code": "US",
                     
                     "mp\_lib": "swift",
                     
                     "mp\_processing\_time\_ms": 1609376952680
                     
                     }
                     
                     }
  ---------------------------------------------------------------------------------------------------

  ------------------------------------------------------------------------------------
  URL                https://data.mixpanel.com/api/2.0/export    
  ------------------ ------------------------------------------- ---------------------
  Input Parameters   from\_date                                  2020-12-29

                     to\_date                                    2020-12-31

                     Event                                       \["Delete Filter"\]

  Response           {
                     
                     "event": "Delete Filter",
                     
                     "properties": {
                     
                     "time": 1609392561,
                     
                     "distinct\_id": "braddu97@gmail.com",
                     
                     "\$app\_build\_number": "1.12.0.4522",
                     
                     "\$app\_version\_string": "1.12.0",
                     
                     "\$carrier": "AT&T",
                     
                     "\$city": "College Station",
                     
                     "\$device\_id": "braddu97@gmail.com",
                     
                     "\$had\_persisted\_distinct\_id": true,
                     
                     "\$insert\_id": "311720dbfcc475ac",
                     
                     "\$lib\_version": "2.7.7",
                     
                     "\$manufacturer": "Apple",
                     
                     "\$model": "iPhone11,8",
                     
                     "\$os": "iOS",
                     
                     "\$os\_version": "14.3",
                     
                     "\$radio": "LTE",
                     
                     "\$region": "Texas",
                     
                     "\$screen\_height": 812,
                     
                     "\$screen\_width": 375,
                     
                     "\$wifi": true,
                     
                     "mp\_country\_code": "US",
                     
                     "mp\_lib": "swift",
                     
                     "mp\_processing\_time\_ms": 1609421366242
                     
                     }
                     
                     }

                                                                 

                                                                 

                                                                 
  ------------------------------------------------------------------------------------

  ---------------------------------------------------------------------------------------------------
  URL                https://data.mixpanel.com/api/2.0/export                  
  ------------------ --------------------------------------------------------- ----------------------
  Input Parameters   from\_date                                                2020-12-29

                     to\_date                                                  2020-12-31

                     Event                                                     \["Device removed"\]

  Response           {
                     
                     "event": "Device removed",
                     
                     "properties": {
                     
                     "time": 1609238558,
                     
                     "distinct\_id": "10be417a-cd8e-45bc-ae5d-1c723ab3d9fe",
                     
                     "\$app\_build\_number": 4213,
                     
                     "\$app\_release": 4213,
                     
                     "\$app\_version": "1.12.0.4213",
                     
                     "\$app\_version\_string": "1.12.0.4213",
                     
                     "\$bluetooth\_enabled": false,
                     
                     "\$bluetooth\_version": "ble",
                     
                     "\$brand": "xiaomi",
                     
                     "\$carrier": "airtel",
                     
                     "\$city": "Hyderabad",
                     
                     "\$device\_id": "d791b834-1d4b-4784-9e17-855b38624bae",
                     
                     "\$distinct\_id\_before\_identity": "346298",
                     
                     "\$google\_play\_services": "available",
                     
                     "\$had\_persisted\_distinct\_id": false,
                     
                     "\$has\_nfc": false,
                     
                     "\$has\_telephone": true,
                     
                     "\$insert\_id": "6481a64e24e4c920",
                     
                     "\$lib\_version": "5.8.4",
                     
                     "\$manufacturer": "Xiaomi",
                     
                     "\$model": "Redmi Note 5 Pro",
                     
                     "\$os": "Android",
                     
                     "\$os\_version": "9",
                     
                     "\$region": "Telangana",
                     
                     "\$screen\_dpi": 440,
                     
                     "\$screen\_height": 2030,
                     
                     "\$screen\_width": 1080,
                     
                     "\$user\_id": "346298",
                     
                     "\$wifi": false,
                     
                     "API success": true,
                     
                     "Device type": "RAP",
                     
                     "User email": "rakeshzalavadiya@gmail.com",
                     
                     "mp\_country\_code": "IN",
                     
                     "mp\_lib": "android",
                     
                     "mp\_processing\_time\_ms": 1609267398709
                     
                     }
                     
                     }
  ---------------------------------------------------------------------------------------------------
