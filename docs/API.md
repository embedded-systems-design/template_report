## Message Compliance

## Messages I send
| **Type**         | **Byte 1** | **Byte 2** | **Byte 3** |
|------------------|-------------|-------------|-------------|
| **Variable Name** | Motor_Speed          | Wave_Freq          | Wave_Length          |
| **Variable Type** | uint8_t     (1)     | uint8_t    (2)     | uint8_t    (3)      |
| **Min Value**      | 0          | .0012 Hz          | 1          |
| **Max Value**      | 14 rpm          | .0104 Hz          | 4.1          |
| **Example**        | 6.1 rpm          | .003 Hz          | 2 meters          |

## Messages I Recieve 

| **Type**         | **Byte 1** | **Byte 2** | **Byte 3** |
|------------------|-------------|-------------|-------------|
| **Variable Name** | Motor_Speed          | Wave_Freq          | Wave_Length          |
| **Variable Type** | uint8_t     (1)     | uint8_t    (2)     | uint8_t    (3)      |
| **Min Value**      | 0          | .0012 Hz          | 1          |
| **Max Value**      | 14 rpm          | .0104 Hz          | 4.1          |
| **Example**        | 6.1 rpm          | .003 Hz          | 2 meters          |

## Messages to whole team

| **Type**         | **Byte 1** | **Byte 2** | **Byte 3** |
|------------------|-------------|-------------|-------------|
| **Variable Name** | Motor_Speed          | Wave_Freq          | Wave_Length          |
| **Variable Type** | uint8_t     (1)     | uint8_t    (2)     | uint8_t    (3)      |
| **Min Value**      | 0          | .0012 Hz          | 1          |
| **Max Value**      | 14 rpm          | .0104 Hz          | 4.1          |
| **Example**        | 6.1 rpm          | .003 Hz          | 2 meters          |


#include "project.h"
#include <stdint.h>

#define MSG_TYPE_SPEED 64
#define MSG_TYPE_FREQ_SET 65
#define MSG_TYPE_FREQ_REPORT 66

#define MIN_SPEED -100
#define MAX_SPEED 100
#define MIN_FREQ 20
#define MAX_FREQ 2000

void sendMessage(uint8_t msgType, uint8_t motorID, int16_t data);
void processMessage(uint8_t* buffer, uint8_t length);

// UART buffer for incoming messages
#define BUFFER_SIZE 32
uint8_t rxBuffer[BUFFER_SIZE];
uint8_t rxIndex = 0;

// Example send function
void sendMessage(uint8_t msgType, uint8_t motorID, int16_t data) {
    uint8_t message[4];
    message[0] = msgType;
    message[1] = motorID;
    message[2] = (uint8_t)(data & 0xFF);        // LSB
    message[3] = (uint8_t)((data >> 8) & 0xFF); // MSB

    UART_PutArray(message, 4);
}

// Example receive handler
void processMessage(uint8_t* buffer, uint8_t length) {
    if (length < 4) return; // Ignore incomplete messages

    uint8_t msgType = buffer[0];
    uint8_t motorID = buffer[1];
    int16_t data = (buffer[3] << 8) | buffer[2];

    switch (msgType) {
        case MSG_TYPE_SPEED:
            if (data >= MIN_SPEED && data <= MAX_SPEED) {
                // Control motor speed logic here
                MotorControl_SetSpeed(motorID, data);
            }
            break;

        case MSG_TYPE_FREQ_SET:
        case MSG_TYPE_FREQ_REPORT:
            if (data >= MIN_FREQ && data <= MAX_FREQ) {
                // Frequency control logic here
                MotorControl_SetFrequency(motorID, data);
            }
            break;

        default:
            // Ignore unknown message types
            break;
    }
}

int main(void) {
    CyGlobalIntEnable;  // Enable interrupts
    UART_Start();       // Start UART module

    for (;;) {
        if (UART_GetRxBufferSize() > 0) {
            rxBuffer[rxIndex++] = UART_GetByte();
            if (rxIndex >= 4) {
                processMessage(rxBuffer, rxIndex);
                rxIndex = 0; // Reset buffer index after processing
            }
        }
    }
}
