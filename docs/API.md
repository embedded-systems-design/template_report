title: API
---

# My Role

Each team member in the daisy chain plays a role in the daisy chain. Their message is denoted by their last name. (l for Larance and so on). My job is to handle the light sensor values, S1 and S2, and display them in the MQTT server and pass the values alongside the 'mode' change to the HMI which then passes it to the other systems as needed.




| Temm members | Unique ID |
|-----|-----|
|Shon Ha        |h|
|Maximus Mathews|m|
|Rohan Fernandez|f|
|Shelton Larance|l|


# Messages Received  

### Message Type 3 (Light Readings from the sensors)

<b><i>Received and Forwarded to MQTT</i></b>

|               | Byte 1-2     | Byte 3-6      | Byte 7-8     | Byte 9-12     |
|---------------|--------------|---------------|--------------|---------------|
| Variable Name | sensor_one   | S1_reading    | sensor_one   | S2_reading    |
| Variable Type | char         | char          | char         | char          |
| Min Value     | S1           | 0000          | S2           | 0000          |
| Max Value     | S1           | 5400          | S2           | 5400          |
| Example       | S1           | 2750          | S2           | 1532          |

# Messages Sent  

### Message Type 1 (Wifi Toggle - Automatic/Manual)

<b><i>Used to toggle stepper motor functionality from automatic (state 0) to manual (state 1).</i></b>

|               | Byte 1      | Byte 2 |
|---------------|-------------|--------|
| Variable Name | mode        | mode_toggle |  
| Variable Type | char        |  char| 
| Min Value     | M           |   0|
| Max Value     | M           |   1|
| Example       | M           |   1|



### ALL messages are to be sent and received as individual Char characters

### Valid Message Examples

|description      | example   |
|---------------|-------------|
| recieved|  AZhlS15400S21345YB          |
| sent|   AZlfM0S15400S23400YB    |  





