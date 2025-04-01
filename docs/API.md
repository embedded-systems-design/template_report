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
| Sivannee | S | Hex (0x53)

[RECEIVERID]: This helps others see who needs to receive the message. 

| Teammates | RECEIVER ID | Type |
| ---------|---------|----------|
|Zack | Z | Hex (0x5A)
|Brendan | B| Hex (0x42)
|Carter | C| Hex (0x43)
| Sivannee | S | Hex (0x53)

[Message type]: Shows what the value is going to be for. Message type is a hex (1-4)

| Message Types | Values | Type |
| ---------|---------|----------|
| Motor Freq | 1 | 0x31 |
| Wavelength | 2 | 0x32 |
| Motor on/off | 3 | 0x33 |
| NA | 4 | 0x34 |

[Value]: Shows the value for the message type that is sending through (Values are based what the message type is. This messages are in hex (0-256).

| Message Types | Values | Type |
| ---------|---------|----------|
| Motor Freq | 0-255 | 0x30 - 0xFF |
| Wavelength | 0-256 | 0x30 - 0xFF |
| Motor on/off | 0-1 | 0x30-0x31 |
| NA | 4 | na |

[YB]: This is the end of the message. This tells the the controller to stop reading the message, all messages needs this to be read. NEEDS TO BE IN HEX (0x59)(0x42)

## Examples

0x41 0x5A 0x43 0x5A 0x31 0x28 0x32 0x30 0x30 0x29 0x59 0x42   Carter sends Zack motor freq of 200 


0x41 0x5A 0x5A 0x42 0x31 0x28 0x31 0x29 0x59 0x42   Zack sends Brendan motor is on

