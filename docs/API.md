title: API
---





# Messages Received  

### Message Type 3 (Voltage Readings)  
This message is received and displayed on the phone.  

|                      | Byte 1          | Byte 2-5           |
|----------------------|----------------|--------------------|
| **Variable Name**    | Voltage_Sensor | Voltage_Reading   |
| **Variable Type**    | Char           | String             |
| **Min Value**       | V              | 0.0               |
| **Max Value**       | V              | 5.0               |
| **Example**         | V              | 3.4               |

---

# Messages Sent  

### Message Type 1 (Automatic/Manual Toggle)  
This message is used to toggle the motor function between state 0 and state 1.  

|                      | Byte 1         |
|----------------------|---------------|
| **Variable Name**    | auto_toggle   |  
| **Variable Type**    | uint8_t       |  
| **Min Value**       | 0             |  
| **Max Value**       | 1             |  
| **Example**         | 1             |  
