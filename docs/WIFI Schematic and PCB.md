title: Schematic/PCB
---

## Final Design


![IMG_6548](https://github.com/user-attachments/assets/2486428a-1d86-4083-94bf-e89d954788d7)

![IMG_6549](https://github.com/user-attachments/assets/42ba48a8-55fd-4947-a306-ca619398150e)



## Schematic WI-FI Two-Way Internet Communication Using MQTT

![image](https://github.com/user-attachments/assets/b50dc292-9f08-4729-be37-c32dfcc6f4c4)






[wifi_schematic_1.pdf](https://github.com/user-attachments/files/20032067/wifi_schematic_1.pdf)




This schematic meets the project's outlined requirements by communicating with the MQTT web server, receiving data, and displaying the values across various locations. This is done through RX and TX UART communication on the board and establishing a web server communication.


## PCB



Top Layer

<img width="268" alt="image" src="https://github.com/user-attachments/assets/5e01db68-9875-4cfb-9b88-5b326a931cc3" />



Bottom Layer

<img width="301" alt="image" src="https://github.com/user-attachments/assets/4db6a076-b345-4568-808b-d9b23df0b5fb" />


Full PCB Image

<img width="301" alt="image" src="https://github.com/user-attachments/assets/94b46763-3ff1-4361-9c3b-915194860bcf" />


[WIFIPCB.pdf](https://github.com/user-attachments/files/19714302/WIFIPCB.pdf)


[Gerber and Drill Files.zip](https://github.com/user-attachments/files/20049250/Gerber.and.Drill.Files.1.zip)



## User Satisfaction
The MQTT subsystem plays a key role in making everything work smoothly behind the scenes. While the motor gets most of the spotlight for physically moving the solar panel, it depends on the data that MQTT helps send and receive. Whether it's light readings from sensors, button presses, or switching between automatic and manual modes, MQTT makes sure that information gets where it needs to go quickly and reliably. Our part in this project is all about keeping those connections strong so the system can respond in real time. This is especially important for showing students in grades K–12 how solar power and smart energy systems work. MQTT even supports two-way communication, so not only can we send sensor data to the motor, but we can also receive commands and updates going the other way. In short, MQTT might not be visible, but it's what keeps all the other subsystems talking—and without that, the whole project wouldn’t come together.


## Decision Making process
THe process of designing MQTT was fairly straightforqard. The biggest decisions regarding this subsystem was how do we impliment the WIFI functionality as effectivly as possible while checking off all requirements. The team steeled on having the WIFI be similar to another HMI system. This means that users would be able to visibly see light values printed on the MQTT server, while also being able to interact and make mode changes with a press of a button. 




## Version 2.0
Looking ahead, there’s a lot of exciting potential for version 2.0 of the MQTT subsystem. Right now, we’re using an ESP32-S3, which is already a strong platform. It gave me plenty of flexibility for handling MQTT tasks. But for a more scalable setup, version 2.0 could offload MQTT responsibilities to a dedicated communication module, like a Raspberry Pi. That would free up the ESP32-S3 to focus more on real-time control and sensor processing while improving the reliability and speed of message handling.
On the hardware side, adding an external antenna or upgrading to a Wi-Fi module with a better range could help in areas with weak WIFI signals, especially useful if the project is used outdoors the way it was intended. Including local storage, like a memory card, would let us buffer MQTT messages during network drops so no data gets lost. If we integrate a real-time clock with a small battery backup, we could timestamp messages and support scheduled publishing, which makes the system feel a lot smarter and more robust.








