---
title: Block Diagram
---

# Block Diagram, Process Diagram, and Message Structure

## Block Diagram

![Figure 1: Team Block Diagram](./TeamBlockDiagram.png)

## Process Diagram

![Figure 2: Communication Process Diagram](./SequenceDiagram.jpg)

## Message Structure

| Message Type <br /> byte 1-2 <br /> (char)            | Description |
| --------------------------------------------- | ----------- |
|1                                              | Set motor X in Y in direction |
|2                                              | Print sensor X value Y |
|3                                              | Subsystem Wifi Error Message |
|4                                              | Subsystem Wifi Status X |
|5                                              | Subsystem X is not communicating |
|6                                              | Motor Status, X |
|7                                              | Sensor Status, X |
|8                                              | Broadcast |

### Message Type 1:

| Byte 1 (uint8_t) | Byte 2 (uint8_t) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7 (char) | Byte 8 (char) | Byte 9 (uint8_t) | Byte 10 (uint8_t) |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | ------------ |
| 0x41 | 0x5a | Source ID (char)| Dest ID (char)| Message Type (char)|  X(char) | Y(char) | 0x59 | 0x42 |

### Message Type 2:

| Byte 1 (uint8_t) | Byte 2 (uint8_t) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7 (char) | Byte 8 (char) | Byte 9 (uint8_t) | Byte 10 (uint8_t) |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | ------------ |
| 0x41 | 0x5a | Source ID (char)| Dest ID (char)| Message Type (char)| X(char) | Y(char) | 0x59 | 0x42 |

### Message Type 3:

| Byte 1 (uint8_t) | Byte 2 (uint8_t) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7-55 (char) | Byte 56 (uint8_t) | Byte 57 (uint8_t) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| 0x41 | 0x5a | Source ID (char)| Dest ID (char)| Message Type (char)| String | 0x59 | 0x42 |

### Message Type 4:

| Byte 1 (uint8_t) | Byte 2 (uint8_t) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7 (uint8_t) | Byte 8 (uint8_t) | Byte 9 (uint8_t) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| 0x41 | 0x5a | Source ID (char)| Dest ID (char)| Message Type (char)| X(uint8_t) | 0x59 | 0x42 |

### Message Type 5:

| Byte 1 (uint8_t) | Byte 2 (uint8_t) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7 (char) | Byte 8 (uint8_t) | Byte 9 (uint8_t) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| 0x41 | 0x5a | Source ID (char)| Dest ID (char)| Message Type (char)|  X(char) | 0x59 | 0x42 |

### Message Type 6:

| Byte 1 (uint8_t) | Byte 2 (uint8_t) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7 (uint8_t) | Byte 8 (uint8_t) | Byte 9 (uint8_t) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| 0x41 | 0x5a| Source ID (char)| Dest ID (char)| Message Type (char)| X(uint8_t) | 0x59 | 0x42 |

### Message Type 7:

| Byte 1 (uint8_t) | Byte 2 (uint8_t) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7 (uint8_t) | Byte 8 (uint8_t) | Byte 9 (uint8_t) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| 0x41 | 0x5a | Source ID (char)| Dest ID (char)| Message Type (char)| X(uint8_t) | 0x59 | 0x42 |

### Message Type 8:

| Byte 1 (uint8_t) | Byte 2 (uint8_t) | Byte 3 (char) | Byte 4 (uint8_t) | Byte 5-6 (char) | Byte 7-55 (char) | Byte 56 (uint8_t) | Byte 57 (uint8_t) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| 0x41 | 0x5a | Source ID (char) | 0x58 | Message Type (char)| String | 0x59 | 0x42 |

#### Wifi Status Code Key

<li>Connected:     1 </li>
<li>Not Connected: 0 </li>