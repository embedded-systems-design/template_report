title: Schematic/Power Budget
---

## Schematic WI-FI Two-Way Internet Communication Using MQTT

<img width="517" alt="image" src="https://github.com/user-attachments/assets/93c11d1a-a5fe-4b64-910f-68626e88b5a4" />





[WIFI_Schematic_1.zip](https://github.com/user-attachments/files/19396605/WIFI_Schematic_1.zip)
[Schematic.pdf](https://github.com/user-attachments/files/19396579/Schematic.pdf)



This schematic meets the project's outlined requirements by communicating with the MQTT web server, receiving data, and displaying the values across various locations. THis is done through RX and TX UART communication on the board and establishing a web server communication.


## Power Budget

![Power Budget](https://github.com/user-attachments/assets/23109ea8-9ecd-4a2a-92ff-b927bc8fe66d)









Since the majority of the power is going to be utilized by the esp32, it is the only component on the 3.3V power line. Since this compnent only uses a max of 95mA out of the available 1000mA from the regulator, Current will not be an issue.
