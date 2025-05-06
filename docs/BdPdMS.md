---
title: Block Diagram
---

### Block Diagram

![Figure 1: Team Block Diagram](./TeamBlockDiagram.png)

While connecting our individual block diagrams together, the team started with which systems needs to be next to each other. That would be the actuator and sensor subsystem, these systems need to be connected to each other to conduct SPI communication to facilitate a feedback loop. All other systems can be placed around these two, as communication will be handled through UART. To communicate through UART and complete product requirements, each individual system has a ribbon cable header. The ribbon cable header has power, ground, and receiving and transmitting pins. We pass these pins to each other to communicate effectively.

### Process Diagram

![Figure 2: Communication Process Diagram](./SequenceDiagram.jpg)

Our communication sequence easily grants the user full control over the stepper motor’s speed and visibility of its current RPM value via the Hall Effect sensor.  This system is designed for intuitive interaction with energy generation processes, so the sequence is built to support user expectations around control, feedback, real time visibility, and accessibility.

The various buttons, and functions per button, and wifi system allow for dual user access (web-based and in-person), so that remote users can engage with the system online while physical ones interact locally.  Along with multi-user operability and control interface consistency, each task of the system is designed to function at the press of a button from either user.  Two buttons send messages to their corresponding neighboring subsystems to control the stepper motor gate and monitor the Hall Effect Sensor all at once.  As the Hall Effect sensor reads new inputs at a fast rate, one of the HMI board’s buttons will switch the OLED screen so the user can view the current value, as well as observe changes in value upon each new button press, providing almost immediate feedback. When the wifi system receives the Hall Effect sensor value it displays it to the user via MQTT, periodically refreshing the value. The target RPM can also be modified upon another button press, which toggles the RPM value between 0 to 100.  Upon selection, the target value is sent to all other boards. The wifi system operates in a similar manner. It receives the targeted RPM from the user over MQTT, the received publication is then passed to the Hall Effect Sensor system to conduct their feedback loop.  

This is a similar process for user control over the stepper motor; a separate button will send messages directly and exclusively to the subsystem responsible for motor control. Web-based users can also interact with the exhibit this way. By publishing a message in MQTT, the user can manipulate the stepper motor into three positions, open, half-open, and closed. The system that contains the wifi receives the publication and sends a message directed to the actuator system, simultaneously updating the MQTT text box that notifies the user that the motor has been set to the user's desired position.  

### Message Structure

| Message Type <br /> 1 Byte <br /> (int8_t)            | Description |
| --------------------------------------------- | ----------- |
|1                                              | Set motor in X position |
|2                                              | Print sensor value, X |
|3                                              | Set target RPM, X |
|4                                              | Broadcast |

#### Team ID

|  | Alex | Luis | Tyler | Frank |
|--|------|------|-------|-------|
|Team Id (char) | a | b | c | d |

#### Message Type 1:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6 (int8_t) | Byte 7 (char) | Byte 8 (char) |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (int8_t) | X(int8_t) | Y | B |

#### Message Type 2:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6 (int8_t) | Byte 7 (char) | Byte 8 (char) |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- | -------------- | ------------ |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (int8_t)| X(int8_t) | Y | B |

#### Message Type 3:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6 (int8_t) | Byte 7 (char) | Byte 8 (char) |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- | -------------- | ------------ |
| A | Z | Source ID (char)| Dest ID (char)| Message Type (int8_t)| X(int8_t) | Y | B |

#### Message Type 4:

| Byte 1 (char) | Byte 2 (char) | Byte 3 (char) | Byte 4 (char) | Byte 5 (int8_t) | Byte 6-55 (string) | Byte 56 (char) | Byte 57 (char) |
| --------------| ------------- | ------------- | ------------- | --------------- | ---------------- | -------------- | ------------ |
| A | Z | Source ID (char) | X | Message Type (int8_t)| String | Y | B |

### Team Verification Table:

| Message Type | Message ID <br /> Type <br /> uint8_t | Alex <br /> Role: HMI <br /> ID: a | Frank <br /> Role: Actuator <br /> ID: c | Tyler <br /> Role: Sensor <br /> ID: d | Luis <br /> Role: MQTT <br /> ID: b |
| --------------| ------------- | ------------- | ------------- | ------------- | --------------- |
| Motor Value | 0x01 | S: Sends message when button is pressed. | R: Lights a single LED. | S: Sends when Target RPM is received. | S: (mqtt topic: /EGR314/TEAM202LS/SUB) |
| Sensor Value | 0x02 | R: Display on OLED. | -  | S: Sends every second. | R: (mqtt topic: /EGR314/TEAM202LS/SENSOR) |
| Target RPM | 0x03 | S: Sends message when button is pressed. | - | R: Lights LED | S: (mqtt topic: /EGR314/TEAM202LS/RPM) |

|Item | Meaning |
|-----| ------- |
| S | Sends the message |
| R | Receives & does something with message |
| - | Do nothing, passes message |

The first approach the team took in designing the message structure was deciding what information is mandatory for each subsystem. After creating our mandatory list of messages, team 202 would then include messages that would help them debug the system in real-time. After all potential messages were created, we then trimmed the list. Most, if not all trimmed messages, include messages that provide information that can be obtained by another message.

Once we had compiled our list of messages, team 202 then discussed the best way to format them. We came to the conclusion that including "message type" in our message structure will ensure that each member will know the context of the message they are receiving. Additionally, we had discussed that it would be inefficient for a device to send the same message to more than one system, so we created those messages to be sent out as a broadcast message as well.

### Top 5 Biggest Changes To API

<li>We originally had 8 messages, broadcast message included. Four messages were dropped as they can be interpreted by another message. Dropping these messages allowed the team to continue developing the exhibit as well as decreases the noise between systems. This also ensures that the only communication happening between systems are priority and necessary.</li>
<li>We changed the message that the actuator system would be receiving. Currently we have the motor accept values 0, 1, or 2. Originally we were gonna have the actuator system accept only values between -1 and 1. So instead of setting the actuator in a predestined position the actuator would respond to a button press.</li>
<li></li>
<li></li>
<li></li>