## Individual Block Diagram

![Untitled Diagram drawio (1)](https://github.com/user-attachments/assets/e3c94f12-4f6b-43bd-9314-657d2d2ddc19)



-------------------------------------------------

Block diagram of the Motor part of the project. There is 2 different voltages on the board, 12 V and 3.3 V. The Microcontroller is connected to the motor driver through the SPI connections. The driver is connected to the stepper motor. 

--------------------------------------------------

Decision Process: The different voltages is an easy decision based on needs the 2 voltages for the motor and the mircocontroller. The Motor driver I used inputs both voiltages for the motor power and the internal CPU. 


One problem I over looked in this process was I thought putting 3.3 volts into pin 1, to connect to others boards. We needed unregulated voltage, likely 9V, so I shouldnt have anything connected. I ended up cutting the lines on my final board.
