---
title: Block Diagram
---

# Block Diagram, Process Diagram, and Message Structure

## Block Diagram

![Figure 1: Team Block Diagram](./TeamBlockDiagram.png)

## Process Diagram

![Figure 2: Communication Process Diagram](./SequenceDiagram.jpg)

## Message Structure

| Message Type <br /> 1 Byte <br /> (int8_t)            | Description |
| --------------------------------------------- | ----------- |
|1                                              | Set motor X in Y in direction |
|2                                              | Print sensor X value Y |
|3                                              | Subsystem Wifi Error Message |
|4                                              | Subsystem Wifi Status X |
|5                                              | Subsystem X is not communicating |
|6                                              | Motor Status, X |
|7                                              | Sensor Status, X |
|8                                              | Broadcast |

### Team ID

|  | Alex | Luis | Frank | Tyler |
|--|------|------|-------|-------|
|Team Id (char) | a | b | c | d |

### Team Verification:

| Message Type | Message ID <br /> Type <br /> uint8_t | Alex <br /> Role: HMI <br /> ID: a | Frank <br /> Role: Actuator <br /> ID: c | Tyler <br /> Role: Sensor <br /> ID: d | Luis <br /> Role: MQTT <br /> ID: b |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- |
| Motor Value | 0x01 | | | | |
| Sensor Value | 0x02 | | | | |
| Wifi Error Message Value | 0x03 | | | | |
| Wifi Status Value | 0x04 | | | | |
| Subsystem Error Message| 0x05 | | | | |
| Motor Status | 0x06 | | | | |
| Sensor Status | 0x07 | | | | |

|Item | Meaning |
|-----| ------- |
| S | Sends the message |
| R | Receives & does something with message |
| - | Do nothing, passes message |

### Message Type 1:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6 (char) | Byte 7 (char) | Byte 8 (char) | Byte 9 (char) |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | ------------ |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (int8_t)|  X(char) | Y(char) | Y | B |

### Message Type 2:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6 (char) | Byte 7 (int8_t) | Byte 8 (char) | Byte 9 (char) |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | ------------ |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (int8_t)| X(char) | Y(int8_t) | Y | B |

### Message Type 3:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6-55 (string) | Byte 56 (char) | Byte 57 (char) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (int8_t)| String | Y | B |

### Message Type 4:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6 (uint8_t) | Byte 7 (char) | Byte 8 (char) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| A | Z  | Source ID (char)| Dest ID (char)| Message Type (int8_t)| X(uint8_t) | Y | B |

### Message Type 5:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6 (char) | Byte 7 (char) | Byte 8 (char) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (int8_t)|  X(char) | Y | B |

### Message Type 6:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6 (uint8_t) | Byte 7 (char) | Byte 8 (char) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (int8_t)| X(uint8_t) | Y | B |

### Message Type 7:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6 (uint8_t) | Byte 7 (char) | Byte 8 (char) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (int8_t)| X(uint8_t) | Y | B |

### Message Type 8:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6-55 (string) | Byte 56 (char) | Byte 57 (char) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | ------------ |
| A | Z | Source ID (char) | X | Message Type (int8_t)| String | Y | B |

#### Wifi Status Code Key

<li>Connected:     1 </li>
<li>Not Connected: 0 </li>