This page is to show messages and message types between team members

Overall Example code: [AZ][SENDERID][RECEIVERID][MESSAGETYPE][VALUE][YB]

## Parts

[AZ]: This is the start of the message. This tells the the controller to start reading the message, all messages needs this to be read. 

[SENDERID]: This helps others see who sent the message. 

| Teammates | SENDER ID |
| ---------|---------|
|Zack | Z|
|Brendan | B|
|Carter | C|
| Sivannee | S |

[RECEIVERID]: This helps others see who needs to receive the message. 

| Teammates | RECEIVER ID |
| ---------|---------|
|Zack | Z|
|Brendan | B|
|Carter | C|
| Sivannee | S |

[Message type]: Shows what the value is going to be for. Message type is a hex (1-4)

| Message Types | Values |
| ---------|---------|
| Motor Freq | 1 |
| Wavelength | 2 |
| Motor on/off | 3 |
| NA | 4 |

[Value]: Shows the value for the message type that is sending through (Values are based what the message type is. This messages are in hex (0-256).

| Message Types | Values | 
| ---------|---------|
| Motor Freq | 0-256 |
| Wavelength | 0-256 |
| Motor on/off | 0-1 |
| NA | 4 |

## Examples

AZCZ11FYB   // Motor Frequency, 1F (31 in decimal)
AZCZ21EYB   // Wavelength, 1E (30 in decimal)
AZCZ300YB   // Motor Off
AZCZ301YB   // Motor On
