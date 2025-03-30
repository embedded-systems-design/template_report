title: API
---

# My Role
EEach team member in the daisy chain phas a role in the daisy chain. Their message is denoted by their last name. (L for Larance and so on). My job is to handle the v as the WIFI is to display voltage, as well as pass on the mode change message to the HMI.

## Team Bytes
| Byte | Function |
|----|-------|
| AZ | Start |
| YB | Stop  |

| Unique ID | Byte |
|-----|-----|
|Shon Ha| H |
|Maximus Mathews|M|
|Rohan Fernandez|F|
|Shelton Larance|L|


# Messages Received  

### Message Type 3 (Voltage Readings from Solar Panel)

<b><i>Received and Forwarded to MQTT</i></b>

|               | Byte 1         | Byte 2-5        |
|---------------|----------------|-----------------|
| Variable Name | voltage_sensor | voltage_reading |
| Variable Type | String         | uint16_t       |
| Min Value     | V              | 0000           |
| Max Value     | V              | 5400           |
| Example       | V              | 2572           |
---

# Messages Sent  

### Message Type 1 (Wifi Toggle - Auto/Manual)

<b><i>Used to toggle stepper motor functionality from automatic (state 0) to manual (state 1).</i></b>

|               | Byte 1      | Byte 2 |
|---------------|-------------|--------|
| Variable Name | mode        | mode_toggle |  
| Variable Type | char        |  uint8_t| 
| Min Value     | M           |   0|
| Max Value     | M           |   1|
| Example       | M           |   1|
