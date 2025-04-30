## Schematic Design
Schematic is for the Stepper motor subsystem 
![Schematic](https://github.com/user-attachments/assets/b3c4dea8-ef0b-482a-9b60-208d41d88e1c)

PDF file: [motorschematic1](https://github.com/user-attachments/assets/b3c4dea8-ef0b-482a-9b60-208d41d88e1c)

## PCB design
Top:
![IMG_6019](https://github.com/user-attachments/assets/a1a112fe-d946-49b7-b149-1d3e7b069486)
Bottom:
![IMG_6020](https://github.com/user-attachments/assets/56a20741-86c8-44ec-ac2d-e78fc75e1cf0)

## Zip file on MpLab X code

[MOTOR.zip.zip](https://github.com/user-attachments/files/19984532/MOTOR.zip.zip)



## Zip File of Gerber

[NewHope.zip](https://github.com/user-attachments/files/19984448/NewHope.zip)






## Power Budget

![Untitled spreadsheet - Sheet1 (1)_page-0001 (1)](https://github.com/user-attachments/assets/33cfeae8-e38f-417e-bd09-71f148c52443)

The 2 A is enough to support the 12 V rail but it doesnt have the full safety net of 25%. Will keep an eye during testing. 



## Functionality of this schematic abd decision making process

The actuator subsystem for the String Machine project is centered around a NEMA 17 stepper motor driven by the TMC5072 motor driver IC. This driver is integrated directly onto the custom PCB and interfaces with the system’s microcontroller via the SPI communication protocol. The use of SPI allows for high-speed, reliable control and feedback between the microcontroller and the motor driver, which is critical for real-time tuning and adjustment of the string’s vibration characteristics.

This design satisfies the user need for precise, bidirectional motion control, which is essential for dynamically adjusting string tension to generate a wide range of audible frequencies. The TMC5072 provides fine-grained microstepping (up to 1/256), current control, and diagnostic feedback, which enables the system to modulate tension with high accuracy and low noise—ideal for producing clean, musical tones.

By choosing to integrate the TMC5072 chip directly onto the PCB, the design minimizes potential issues related to mechanical stability, trace length, and signal reflections—thereby improving long-term reliability. This also allows for a compact and professional layout that’s easier to debug and maintain.

Furthermore, powering the motor with a dedicated 12V rail ensures the NEMA 17 motor can deliver the necessary torque to manipulate the string under tension without stalling or losing steps. This directly supports the product requirement for consistent and smooth motion over a wide range of frequencies.

Overall, the schematic aligns with all core functional and user requirements: serial programmability, accurate motor positioning, mechanical robustness, and high-frequency resolution. These ensure the system can produce human-audible sound waves reliably, which is the central goal of the String Machine.
## Decision Making Process


## Version 2.0 

If I were to create a “Version 2.0” of my hardware design, I would make several critical improvements to enhance reliability, functionality, and debuggability. Although the original board was mostly functional—aside from failing to drive the motor—there were key hardware issues that created unnecessary setbacks during development and testing.

One of the major issues I encountered was the lack of available I/O pins on the PIC microcontroller. In the original schematic, I did not allocate general-purpose output headers for unused pins, which significantly limited my ability to expand the design later. For example, when I wanted to add status LEDs to indicate motor direction, error states, or UART communication activity, there were no spare pins available to connect them. In Version 2.0, I would break out every I/O pin to a test header, even if not used initially, to allow more flexibility for late-stage debugging or added features.

Another major problem was related to the voltage regulator. Allegro failed to properly associate a footprint with the regulator component, which meant that while it was present in the schematic, it had no physical layout on the PCB. As a result, the part was essentially “dangling” off the board, requiring messy rework to test the power supply. For Version 2.0, I would double-check all symbol-to-footprint mappings before finalizing the layout and use ERC/DRC tools more thoroughly to catch these mismatches before manufacturing.

Additionally, my SPI and motor driver connections lacked breakout pins for signal probing. When the motor didn’t respond, I had no way to easily observe what was being transmitted over MOSI, MISO, or the state of chip select. In the redesign, I would add test points or 0.1" header breakouts for SPI lines and motor driver signals so I could use an oscilloscope or logic analyzer to verify communication in real-time.

Lastly, the footprint used for the Snap programmer header was incorrect. This caused poor alignment and unreliable connections every time I tried to flash the microcontroller, costing significant time during development. In Version 2.0, I would replace this with the official Microchip ICSP 5-pin footprint or a keyed connector to ensure consistent and secure programming.

Overall, these improvements would lead to a more robust, testable, and maintainable hardware platform that could be more easily adapted for future revisions or feature enhancements.
