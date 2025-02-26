---
title: Block Diagram
---

# Block Diagram, Process Diagram, and Message Structure

## Block Diagram

![Figure 1: Team Block Diagram](./TeamBlockDiagram.jpg)

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

### Message Type 1:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7 (char) | Byte 8 (char) | Byte 9 (char) | Byte 10 (char) |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | ------------ |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (char)|  X(char) | Y(char) | B | Y |

### Message Type 2:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7 (char) | Byte 8 (char) | Byte 9 (char) | Byte 10 (char) |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | ------------ |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (char)| X(char) | Y(char) | B | Y |

### Message Type 3:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7-55 (char) | Byte 56 (char) | Byte 57 (char) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (char)| String | B | Y |

### Message Type 4:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7 (uint8_t) | Byte 8 (char) | Byte 9 (char) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (char)| X(uint8_t) | B | Y |

### Message Type 5:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7 (char) | Byte 8 (char) | Byte 9 (char) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (char)|  X(char) | B | Y |

### Message Type 6:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7 (uint8_t) | Byte 8 (char) | Byte 9 (char) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (char)| X(uint8_t) | B | Y |

### Message Type 7:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5-6 (char) | Byte 7 (uint8_t) | Byte 8 (char) | Byte 9 (char) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | --------- |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (char)| X(uint8_t) | B | Y |
