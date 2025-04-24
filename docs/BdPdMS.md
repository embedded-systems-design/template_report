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
|1                                              | Set motor in X position |
|2                                              | Print sensor value, X |
|3                                              | Set target RPM, X |
|4                                              | Broadcast |

### Team ID

|  | Alex | Luis | Frank | Tyler |
|--|------|------|-------|-------|
|Team Id (char) | a | b | c | d |

### Message Type 1:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6 (char) | Byte 7 (char) | Byte 8 (char) | 
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (int8_t) | X(char) | Y | B |

### Message Type 2:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6 (int8_t) | Byte 7 (char) | Byte 8 (char) |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- | -------------- | ------------ |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (int8_t)| X(int8_t) | Y | B |

### Message Type 3:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6 (int8_t) | Byte 7 (char) | Byte 8 (char) |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- | -------------- | ------------ |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (int8_t)| X(int8_t) | Y | B |

### Message Type 4:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6-55 (string) | Byte 56 (char) | Byte 57 (char) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | ------------ |
| A | Z | Source ID (char) | X | Message Type (int8_t)| String | Y | B |

## Team Verification Table:

| Message Type | Message ID <br /> Type <br /> uint8_t | Alex <br /> Role: HMI <br /> ID: a | Frank <br /> Role: Actuator <br /> ID: c | Tyler <br /> Role: Sensor <br /> ID: d | Luis <br /> Role: MQTT <br /> ID: b |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- |
| Motor Value | 0x01 | S: | R: | - | S: (mqtt topic: /EGR314/TEAM202LS/SUB) |
| Sensor Value | 0x02 | R: | -  | S: | R: (mqtt topic: /EGR314/TEAM202LS/SENSOR) |
| Target RPM | 0x03 | S: | - | R: | S: (mqtt topic: /EGR314/TEAM202LS/RPM) |

|Item | Meaning |
|-----| ------- |
| S | Sends the message |
| R | Receives & does something with message |
| - | Do nothing, passes message |
