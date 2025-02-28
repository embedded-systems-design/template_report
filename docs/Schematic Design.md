## Schematic Design
Schematic is for the Stepper motor subsystem 

![motorschematic1_page-0001](https://github.com/user-attachments/assets/34467786-34d1-4d06-9a48-890eb861097d)

Zip file: [firstschematicfeb27.zip](https://github.com/user-attachments/files/19020154/firstschematicfeb27.zip)

PDF file: [motorschematic1](https://github.com/user-attachments/assets/77e95345-69eb-439d-b6ea-bce9ee8f3d99)






## Power Budget



![Untitled spreadsheet - Sheet1 (1)_page-0001 (1)](https://github.com/user-attachments/assets/33cfeae8-e38f-417e-bd09-71f148c52443)

The 2 A is enough to support the 12 V rail but it doesnt have the full safety net of 25%. Will keep an eye during testing. 


## Functionality of this schematic

The actuator subsystem for the String Machine project features a NEMA 17 stepper motor controlled by the TMC5072 motor driver, which communicates with the system’s microcontroller via SPI. This setup ensures precise bidirectional control, allowing the motor to adjust the string tension dynamically to produce different sound waves. The TMC5072’s integration into the PCB, rather than using a breakout board, enhances reliability and reduces potential signal integrity issues. Additionally, the motor operates at 12V, ensuring sufficient torque while maintaining efficiency. This configuration meets the project’s requirement for a serially controlled actuator while providing smooth and accurate motion for the string tensioning mechanism.

