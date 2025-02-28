title: Schematic/Power Budget
---

## Schematic WI-FI Two-Way Internet Communication Using MQTT

<img width="575" alt="image" src="https://github.com/user-attachments/assets/2057e4ff-bf2a-4eeb-9baa-70b857ee313a" />


[WIFI_Schematic_1.zip](https://github.com/user-attachments/files/18918472/WIFI_Schematic_1.zip)  
[WIFI_Schematic.pdf](https://github.com/user-attachments/files/18998511/Screenshot.2025-02-26.155826.pdf)


This schematic meets the project's outlined requirements by communicating with the MQTT web server, receiving data, and displaying the values across various locations. THis is done through RX and TX UART communication on the board and establishing a web server communication.


## Power Budget

![Power Budget](https://github.com/user-attachments/assets/23109ea8-9ecd-4a2a-92ff-b927bc8fe66d)

Since the majority of the power is going to be utilized by the esp32, it is the only component on the 3.3V power line. Since this compnent only uses a max of 95Ma out of the available 1000mA from the regulator, Current will not be an issue.
