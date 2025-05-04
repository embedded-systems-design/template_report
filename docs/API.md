title: API
---

# My Role
Each team member in the daisy chain phas a role in the daisy chain. Their message is denoted by their last name. (L for Larance and so on). My job is to handle the v as the WIFI is to display voltage, as well as pass on the mode change message to the HMI.



| Temm members | Unique ID |
|-----|-----|
|Shon Ha| h |
|Maximus Mathews|m|
|Rohan Fernandez|f|
|Shelton Larance|l|


# Messages Received  

### Message Type 3 (Voltage Readings from Solar Panel)

<b><i>Received and Forwarded to MQTT</i></b>

|               | Byte 1-2     | Byte 3-6      | Byte 7-8     | Byte 9-12     |
|---------------|--------------|---------------|--------------|---------------|
| Variable Name | light_sensor | light_reading | light_sensor | light_reading |
| Variable Type | char         | char          | char         | char          |
| Min Value     | S1           | 0000          | S2           | 0000          |
| Max Value     | S1           | 5400          | S2           | 5400          |
| Example       | S1           | 2750          | S2           | 1532          |

# Messages Sent  

### Message Type 1 (Wifi Toggle - Auto/Manual)

<b><i>Used to toggle stepper motor functionality from automatic (state 0) to manual (state 1).</i></b>

|               | Byte 1      | Byte 2 |
|---------------|-------------|--------|
| Variable Name | mode        | mode_toggle |  
| Variable Type | char        |  char| 
| Min Value     | M           |   0|
| Max Value     | M           |   1|
| Example       | M           |   1|



### ALL messages are to be sent and received as individual Char characters

### Some Valid Message Examples

|description      | example   |
|---------------|-------------|
| recieved|  AZhlS15400S21345YB          |
| sent|   AZlfM0S15400S23400YB    |  





