## Message Types Diagram

This page is to show messages and message types between team members

Overall Example code: [AZ][SENDERID][RECEIVERID][MESSAGETYPE][VALUE][YB]

## Parts

[AZ]: This is the start of the message. This tells the the controller to start reading the message, all messages needs this to be read. NEEDS TO BE IN HEX (0x41)(0x5A)

[SENDERID]: This helps others see who sent the message. 

| Teammates | SENDER ID | Type |
| ---------|---------|----------|
|Zack | Z| Hex (0x5A)
|Brendan | B| Hex (0x42)
|Carter | C| Hex (0x43)


[RECEIVERID]: This helps others see who needs to receive the message. 

| Teammates | RECEIVER ID | Type |
| ---------|---------|----------|
|Zack | Z | Hex (0x5A)
|Brendan | B| Hex (0x42)
|Carter | C| Hex (0x43)
| Everyone | E | Hex (0x45)


[Message type]: Shows what the value is going to be for. Message type is a hex (1-4)

| Message Types | Values | Type |
| ---------|---------|----------|
| Motor Freq | 1 | 0x31 |
| Motor on/off | 3 | 0x33 |
| System off | 4 | 0x34 |

[Value]: Shows the value for the message type that is sending through (Values are based what the message type is. This messages are in hex (0-256).

| Message Types | Values | Type |
| ---------|---------|----------|
| Motor Freq | 0-255 | 0x30 - 0xFF |
| Motor on/off | 0-1 | 0x30-0x31 |
| System off | 0-1 | 0x30-0x31 |
| Sensor Error | 0-6 |  0x30-0x35 |
| Motor Error | 0-6 |  0x30-0x35 |
| Mqtt Error | 0-6 |  0x30-0x35 |

[Error tpye]

| Error Type | Value|
|---|---|
| Wrong Start of message | 0x30 |
| Wrong sender | 0x31 |
| Wrong reciever | 0x32 |
| Wrong message type | 0x33 |
| Wrong message value | 0x34 |
| Wrong End of message | 0x35 | 

[YB]: This is the end of the message. This tells the the controller to stop reading the message, all messages needs this to be read. NEEDS TO BE IN HEX (0x59)(0x42)

---
| Message Type | Message ID  (uint8_t) | Carter Role: Sensor; ID: C | Zack Role: Motor; ID: Z | Brenden Role Web; ID: B |
|---|----|----|-----|---|
| Pitch Value | 0x31 | S (reads sound) | R (Motor reacts) | R (mqtt topic:/ EGR314/TEAM2/PITCH) |
| Motor on or off | 0x33 | - | S (motor spins) | R (mqtt topic: /EGR314/TEAM203/MOTORON |
| System off | 0x34 | R (turn off sensor) | R (Turn motor off ) | S mqtt topic: /EGR314/TEAM203/OFF |
| Sensor Error | 0x35 | S (message error) | R (remove motor SPI ) | R mqtt topic: /EGR314/TEAM203/SENSORERROR |
| Motor Error | 0x36 | R (disconnect sensor) | S (message error ) | R mqtt topic: /EGR314/TEAM203/MOTORERROR |
| Mqtt Error | 0x37 | - | - | R mqtt topic: /EGR314/TEAM203/MQTTERROR |


Table

| Item | Meaning |
|---|---|
| S | Sends the message |
| R | Receives |
| - | Do nothing, pass through |
