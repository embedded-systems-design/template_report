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

|               | Byte 1         | Byte 2        |
|---------------|----------------|-----------------|
| Variable Name | voltage_sensor | voltage_reading |
| Variable Type | char           | uint8          |
| Min Value     | V              | 0           |
| Max Value     | V              | 5          |
| Example       | V              | 3          |

# Messages Sent  

### Message Type 1 (Wifi Toggle - Auto/Manual)

<b><i>Used to toggle stepper motor functionality from automatic (state 0) to manual (state 1).</i></b>

|               | Byte 1      | Byte 2 |
|---------------|-------------|--------|
| Variable Name | mode        | mode_toggle |  
| Variable Type | char        |  uint8| 
| Min Value     | M           |   0|
| Max Value     | M           |   1|
| Example       | M           |   1|





### all Message Type  Examples

|description      | example   |
|---------------|-------------|
| voltage '5' from 's' |  AZsV\x06\x00YB           |
| voltage '2' from 'm' |   AZmV\x02\x00YB     |  
| mode 1 from 's'    |   AZsM\x01YB         | 
|  mode 0 from 's'     |  AZsM\x00YB          | 




