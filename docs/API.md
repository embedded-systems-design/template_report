
##Messages Recieved

  Message Type 3 (Voltage Readings)
  Recieved and displayed on phone

|                      | Byte 1                                | Byte 2-5 |
|----------------------|---------------------------------------|-------|
| Variable Name        | Voltage_Sensor                       | Voltage_Reading     |
| Variable Type        | Char                                 | Float    |
| Min Value            | V                                    | 0.0     |
| Max Value            | V                                    | 5.0     |
| Example              | V                                    | 3.4     |





##Messages Sent

 Message Type 1 (automatic/manual toggle)
 message sent to HMI System
|                      | Byte 1                                
|----------------------|---------------------------------------|
| Variable Name        | auto_toggle                          | 
| Variable Type        | uint8_t                              | 
| Min Value            | 1                                    | 
| Max Value            | 0                                    | 
| Example              | 1                                    |      
