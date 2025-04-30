## Zip File

[MOTOR.zip.zip](https://github.com/user-attachments/files/19984589/MOTOR.zip.zip)



## MpLab Code

#ifndef _XTAL_FREQ
#define _XTAL_FREQ 16000000UL
#endif

#include "mcc_generated_files/system/system.h"
#include <stdbool.h>
#include <stdint.h>

// —— Framing bytes —————————————————————————————
#define START1   0x41  // 'A'
#define START2   0x5A  // 'Z'
#define END1     0x59  // 'Y'
#define END2     0x42  // 'B'

// —— Node IDs ———————————————————————————————————————
typedef enum {
    ID_ZACK    = 0x5A,  // 'Z'
    ID_BRENDAN = 0x42,  // 'B'
    ID_CARTER  = 0x43,  // 'C'
    ID_ALL     = 0x45   // 'E'
} NodeID_t;

// —— Message types ————————————————————————————————
typedef enum {
    MT_FREQ         = 0x31,  // Motor Frequency
    MT_ONOFF        = 0x33,  // Motor On/Off
    MT_SYSOFF       = 0x34,  // System Off
    MT_SENSOR_ERROR = 0x35,  // Sensor Error
    MT_MOTOR_ERROR  = 0x36,  // Motor Error
    MT_MQTT_ERROR   = 0x37   // MQTT Error
} MessageType_t;

// —— Decode error codes ————————————————————————————
typedef enum {
    ERR_NONE     =  0,
    ERR_START    =  2,
    ERR_SENDER   =  3,
    ERR_RECEIVER =  4,
    ERR_TYPE     =  5,
    ERR_VALUE    =  6,
    ERR_END      =  7
} MsgError_t;

// —— Heartbeat packet ————————————————————————————
static const uint8_t heartbeatMsg[8] = {
    START1, START2,
    ID_ZACK,       // sender
    ID_BRENDAN,    // receiver
    MT_ONOFF,      // Motor On/Off
    0x31,          // value = 1
    END1,  END2
};

// —— Map parsing error to sub-code ————————————————————
static uint8_t mapErrorToValue(MsgError_t err) {
    switch (err) {
        case ERR_START:    return 0x30;
        case ERR_SENDER:   return 0x31;
        case ERR_RECEIVER: return 0x32;
        case ERR_TYPE:     return 0x33;
        case ERR_VALUE:    return 0x34;
        case ERR_END:      return 0x35;
        default:           return 0x30;
    }
}

// —— Encode a message into an 8-byte buffer —————————————
static void encodeMessage(NodeID_t sender,
                          NodeID_t receiver,
                          MessageType_t type,
                          uint8_t value,
                          uint8_t outBuf[8])
{
    outBuf[0] = START1;
    outBuf[1] = START2;
    outBuf[2] = (uint8_t)sender;
    outBuf[3] = (uint8_t)receiver;
    outBuf[4] = (uint8_t)type;
    outBuf[5] = value;
    outBuf[6] = END1;
    outBuf[7] = END2;
}

// —— Decode & validate an 8-byte buffer ——————————————————
static MsgError_t decodeMessage(const uint8_t buf[8],
                                NodeID_t *sender,
                                NodeID_t *receiver,
                                MessageType_t *type,
                                uint8_t *value)
{
    if (buf[0] != START1 || buf[1] != START2) return ERR_START;

    *sender = (NodeID_t)buf[2];
    if (*sender!=ID_ZACK && *sender!=ID_BRENDAN && *sender!=ID_CARTER)
        return ERR_SENDER;

    *receiver = (NodeID_t)buf[3];
    if (*receiver!=ID_ZACK && *receiver!=ID_BRENDAN &&
        *receiver!=ID_CARTER && *receiver!=ID_ALL)
        return ERR_RECEIVER;

    *type = (MessageType_t)buf[4];
    if (*type!=MT_FREQ && *type!=MT_ONOFF && *type!=MT_SYSOFF &&
        *type!=MT_SENSOR_ERROR && *type!=MT_MOTOR_ERROR && *type!=MT_MQTT_ERROR)
        return ERR_TYPE;

    *value = buf[5];
    if ((*type==MT_ONOFF || *type==MT_SYSOFF) && *value>1)
        return ERR_VALUE;

    if (buf[6]!=END1 || buf[7]!=END2) return ERR_END;

    return ERR_NONE;
}

// —— Send raw 8-byte message over UART ——————————————————
static void sendRawMessage(const uint8_t buf[8]) {
    for (int i = 0; i < 8; i++) {
        while (!EUSART2_IsTxReady());
        EUSART2_Write(buf[i]);
    }
    while (!EUSART2_IsTxDone());
}

// —— MAIN ——————————————————————————————————————————
void main(void) {
    SYSTEM_Initialize();
    EUSART2_Initialize();

    bool     heartbeatSent    = false;
    bool     heartbeatEnabled = true;
    uint32_t heartbeatCounter = 0;  // ms via __delay_ms(1)

    uint8_t  rxBuf[8];
    uint8_t  rxIndex = 0;

    while (1) {
        // — Heartbeat: first on TX-ready, then every 10 s —
        if (heartbeatEnabled) {
            if (!heartbeatSent && EUSART2_IsTxReady()) {
                sendRawMessage(heartbeatMsg);
                heartbeatSent    = true;
                heartbeatCounter = 0;
            }
            else if (heartbeatSent && heartbeatCounter >= 10000) {
                sendRawMessage(heartbeatMsg);
                heartbeatCounter = 0;
            }
        }

        // — Process incoming 8-byte frames —
        if (EUSART2_IsRxReady()) {
            rxBuf[rxIndex++] = EUSART2_Read();

            if (rxIndex >= 8) {
                MsgError_t    err;
                NodeID_t      snd, rcv;
                MessageType_t mt;
                uint8_t       val;

                // decode & handle errors
                err = decodeMessage(rxBuf, &snd, &rcv, &mt, &val);

                if (err != ERR_NONE) {
                    uint8_t errMsg[8];
                    encodeMessage(
                        ID_ZACK, ID_ALL,
                        MT_MOTOR_ERROR,
                        mapErrorToValue(err),
                        errMsg
                    );
                    sendRawMessage(errMsg);
                }
                else {
                    // special case: Brendan→Everyone SYSOFF=1
                    if (snd==ID_BRENDAN && rcv==ID_ALL &&
                        mt == MT_SYSOFF && val==0x31)
                    {
                        uint8_t reply[8];
                        encodeMessage(
                            ID_ZACK,
                            ID_BRENDAN,
                            MT_ONOFF,
                            0x30,  // “0” = off
                            reply
                        );
                        sendRawMessage(reply);
                        heartbeatEnabled = false;
                    }
                    // otherwise valid message for you—handle internally…
                }

                rxIndex = 0;  // reset for next frame
            }
        }

        // software “tick” for heartbeat timing
        __delay_ms(1);
        if (heartbeatSent && heartbeatEnabled) {
            heartbeatCounter++;
        }
    }
}
