## Component Selection Report

## Summary Table of major components

| Component type | My pick |
|-----|-----------|
| Mircocontroller | PIC18F47Q10-E/MP |
| Voltage Regulation | NCV2575D2T-12R4G |
| Motor Driver | TMC5072 Stepper Motor Driver |
| Motor Stepper | NEMA 17 Stepper Motor |


## Decision Making Process

Main decision for picking the PIC was at the time, we only used the pic and I knew how to work it and was comfortable with it. If I were to do it over again I would use the PIC again. But add more output pins to see if everything was working correctly.

I chosose the voltage regulator I picked because it met all the product requirements. Switching regualator, 12 V to 3.3 V, surface mounted, and can hold 2 A. I would pick this one again, I had no problems with this. 

I picked the TMC5072 motor driver, it was an easy pick because it was able to have 2 motors and used SPI. All the research said this driver could support a fast motor. I would not pick this again, although I got it to receive SPI data, I couldnt get it to turn the motor. I beleive because it required 8 lines of commend to setup the motor, and the pic wasnt able to send it correctly. I would pick the in class motor driver and use 2 of them and try to run them at the same time. 

NEMA 17 is a great motor. I picked this one because it needed low current and was able to hold a wave movement. I would use this again. 


### Motor Selection
| Motor Type               | Pros                                              | Cons                               | Cost    | Datasheet/Buy Link                                                                                                                                      | Picture                                                                                                                                                                |
|--------------------------|---------------------------------------------------|------------------------------------|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NEMA 17 Stepper Motor    | Widely used in similar projects, ample tutorials available | Not available on Digikey           | $14 (x2) | [Datasheet](https://pages.pbclinear.com/rs/909-BFY-775/images/Data-Sheet-Stepper-Motor-Support.pdf) / [Buy](https://www.amazon.com/STEPPERONLINE-Stepper-Bipolar-Connector-compatible/dp/B00PNEQKC0/) | ![1528_324](https://github.com/user-attachments/assets/f9ac0fa9-f200-491b-89f6-a2ba6b77fc1f)                                                                 |
| 324 Stepper Motor Hybrid | Available on Digikey, compatible with 12V power   | Fewer online resources and tutorials | $14 (x2) | [Datasheet](https://cdn-shop.adafruit.com/product-files/324/C140-A+datasheet.jpg) / [Buy](https://www.digikey.com/en/products/detail/adafruit-industries-llc/324/5022791) | ![SM-42HB34F08AB_web(640x640)](https://github.com/user-attachments/assets/dea06de5-138a-4b8b-bfbd-8bd6141bd081) |
| NEMA 23 Stepper Motor    | High torque, holds position well, simple controls | Limited response time, more expensive | $31 (x2) | [Datasheet](https://cdn-shop.adafruit.com/product-files/5117/5117_Stepper_Motor_Data_Sheet.pdf) / [Buy](https://www.digikey.com/en/products/detail/adafruit-industries-llc/5117/14639999) | ![images](https://github.com/user-attachments/assets/94a10a92-74e1-408c-889b-1617955560cd) |

### Motor Driver Selection
| Motor Driver             | Pros                                                  | Cons                                          | Cost    | Datasheet/Buy Link                                                                                                                                             | Picture                                                                                                                                                                      |
|--------------------------|-------------------------------------------------------|-----------------------------------------------|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DRV8825 Stepper Motor Driver | High current capacity (2.5A peak), Microstepping support (up to 1/32), Widely used with tutorials available | Requires heat dissipation for higher currents | ~$8     | [Datasheet](https://www.ti.com/lit/ds/symlink/drv8825.pdf) / [Buy Link](https://www.digikey.com/en/products/detail/soldered-electronics/333000/21293657?gclsrc=aw.ds&&utm_adgroup=&utm_source=google&utm_medium=cpc&utm_campaign=PMax%20Shopping_Product_Low%20ROAS%20Categories&utm_term=&utm_content=&utm_id=go_cmp-20243063506_adg-_ad-__dev-c_ext-_prd-21293657_sig-CjwKCAiA2JG9BhAuEiwAH_zf3sFXmcbqJmnJGvzkRu3IseDg62oV99ovmgCdY3IPeuIMjStmdnqLUBoCEgYQAvD_BwE&gad_source=1&gclid=CjwKCAiA2JG9BhAuEiwAH_zf3sFXmcbqJmnJGvzkRu3IseDg62oV99ovmgCdY3IPeuIMjStmdnqLUBoCEgYQAvD_BwE&gclsrc=aw.ds) | ![download](https://github.com/user-attachments/assets/7c3105ec-3c36-4e0b-98a5-49d55abe30a3) |
| A4988 Stepper Motor Driver | Simple to use, Supports microstepping (up to 1/16), Affordable | Lower current limit (2A peak), Less efficient cooling | ~$5     | [Datasheet](https://www.digikey.com/htmldatasheets/production/1783478/0/0/1/tmc5072-datasheet.pdf)| ![download](https://github.com/user-attachments/assets/17f12af7-2d7b-4931-8970-5298028744af) |
| TMC5072 Stepper Motor Driver | High power handling (3A peak), Good heat dissipation, 2 motor, Adjustable current settings, SPI | Bulky, More expensive                         | ~$15    | [Datasheet](https://www.analog.com/media/en/technical-documentation/data-sheets/tmc2130_datasheet_rev1.15.pdf) / [Buy Link](https://www.digikey.com/en/products/detail/watterott-electronic-gmbh/20160027-002/10071145?gclsrc=aw.ds&&utm_adgroup=&utm_source=google&utm_medium=cpc&utm_campaign=PMax%20Shopping_Product_Low%20ROAS%20Categories&utm_term=&utm_content=&utm_id=go_cmp-20243063506_adg-_ad-__dev-c_ext-_prd-10071145_sig-CjwKCAiA5eC9BhAuEiwA3CKwQktQRARnkVRENUIW5yHmDuYpy1UAJi4NL2xmV22WrdqwAE428-uHRBoChCYQAvD_BwE&gad_source=1&gclid=CjwKCAiA5eC9BhAuEiwA3CKwQktQRARnkVRENUIW5yHmDuYpy1UAJi4NL2xmV22WrdqwAE428-uHRBoChCYQAvD_BwE&gclsrc=aw.ds) | ![MFG_TMC5072-BOB](https://github.com/user-attachments/assets/fbb66003-d9b0-4fc0-8b72-2366b03aab12)  |



### Power Supply & Regulation
| Component                | Pros                                                | Cons                                           | Cost | Datasheet/Buy Link                                                                                                                                  |
|--------------------------|-----------------------------------------------------|------------------------------------------------|------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| LM7805 (5V Regulator)    | Simple, widely available                            | Inefficient linear regulator                   | $1   | [Datasheet](https://www.ti.com/lit/ds/symlink/lm7805.pdf) |
|NCV2575D2T-12R4G (Switching Regulator) | High efficiency, 2 A, 12 V, goes to 3.3 V          | Requires external components                   | $3   | [Datasheet](https://www.monolithicpower.com/en/documentview/productdocument/index/version/2/document_type/Datasheet/lang/en/sku/MP1584) |

### Pinout Table

| **Peripheral**           | **Pin(s)**  | **Description**                            |
|--------------------------|-------------|--------------------------------------------|
| **Power**                | 2 (3V3)     | Main power supply (3.3V).                 |
|                          | 1 (GND)     | Ground connection.                        |
| **UART**                 | 43 (GPIO43) | UART0 TXD (Transmit Data).                |
|                          | 44 (GPIO44) | UART0 RXD (Receive Data).                |
| **SPI**                  | 36 (GPIO36) | SPI_MISO (Master In Slave Out).           |
|                          | 35 (GPIO35) | SPI_MOSI (Master Out Slave In).           |
|                          | 37 (GPIO37) | SPI_CLK (Clock).                          |
|                          | 34 (GPIO34) | SPI_CS (Chip Select).                     |
| **ADC**                  | 1 (GPIO1)   | ADC1 Channel 0.                            |
| **DAC**                  | 17 (GPIO17) | DAC1 output.                               |
| **PWM**                  | 2 (GPIO2)   | PWM output                                 |
| **GPIO**                 | 3 (GPIO3)   | General-purpose input/output (Buttons, LEDs). |

### Final Pin Count Estimation

| **Category**             | **Estimated Pins** |
|--------------------------|--------------------|
| **SPI** (MOSI, MISO, CLK, CS)  | 4 |
| **UART (TX, RX)**        | 2 |
| **Power (3.3V, GND x2)** | 3 |
| **Motor Driver (DIR, STEP, EN)** | 3 |
| **ADC (Optional)**       | 1 |
| **DAC (Optional)**       | 1 |
| **PWM (LEDs, Motor Speed)** | 1 |
| **GPIO (Buttons, Indicators)** | 2 |
| **Programming & Debugging** | 2–4 |

### Rationale for Selections
- **Motor Selection:** NEMA 17 is chosen due to extensive documentation, ease of programming, and cost-effectiveness.
- **Motor Driver:** TMC5072 provides efficient operation with high current handling, suitable for your application.
- **Microcontroller:** The PIC18F47Q10 offers strong wireless capabilities and sufficient GPIOs for the project.
- **Power Regulation:** NCV2575D2T-12R4G is selected for its high efficiency and adjustable voltage output, ideal for powering the system.

## 2) Pick the microcontroller

A. I have use SPI commucation from the microcontroller to the motor driver. Uart connection to teammates. Overall, there will be 13 pins. 4 SPI, 2 UART, 3 Voltage, 2 ground, and 2 snap pins.

B. 
## Pic Info

| **Parameter**                          | **Answer**  | **Help**  |
|----------------------------------------|------------|-----------|
| **Model**                              |  PIC18F27/47Q10          | Include the entire part number (leave off any letters at the end that specify the package type) |
| **Product Page URL**                   |      [Page](https://www.microchip.com/en-us/product/pic18f2580)  | Do not paste links directly into the table. Use a link |
| **Datasheet URL(s)**                    |      [Datasheet]([https://example.com/datasheet.pdf](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27-47Q10-Data-Sheet-40002043E.pdf))        | Do not paste links directly into the table. Use a link |
| **Vendor Link**                         | [digikey](https://www.digikey.com/en/products/detail/microchip-technology/PIC18F2580-I-SP/718241)          | Digikey, Jameco, etc. Do not paste links directly into the table. Use a link |
| **Code Examples**                       | CLRF PORTC ; Initialize PORTC by; clearing output; data latchesCLRF LATC ; Alternate method; to clear output; data latchesMOVLW 0CFh ; Value used to; initialize data; directionMOVWF TRISC ; Set RC<3:0> as inputs; RC<5:4> as outputs; RC<7:6> as inputs          | URL(s) for libraries on GitHub or other sites related to the microcontroller and your planned peripherals || **External Resources URL(s)**            | ?          | Search on Google and YouTube for other resources for each specific microcontroller. |
| **Unit Cost**                           | $2.52          | Find in the Microchip online store or Digikey |
| **Absolute Maximum Current for entire IC** |  4.7 μF to 47 μF     | Find in the microcontroller datasheet |
| **Supply Voltage Range**                | 1.8V ~ 5.5V         | Min / Nominal / Max / Absolute Max, as found in datasheet |
| **Absolute Maximum Current (for entire IC)** |  4.7 μF to 47 μF | As found in datasheet |
| **Maximum GPIO Current (per pin)**      | 4.7 μF to 47 μF          | As found in datasheet |
| **Supports External Interrupts?**       | Yes          | As found in datasheet |
| **Required Programming Hardware, Cost, URL** | Snap  | Found on the microcontroller's product page |
| **Works with MPLabX?**                  | Yes          | Required. See Microchip Development Tools |
| **Works with Microchip Code Configurator?** | Yes  | Can be validated in MPLabX. Screenshot required. |

## Module Availability

| **Module**  | **# Available** | **Needed** | **Associated Pins (or * for any)** |
|------------|--------------|----------|--------------------------------|
| **GPIO**   | 35           | 0        | *                              |
| **ADC**    | 28           | 0        | *                              |
| **UART**   | 2            | 2        | RC6 (TX), RC7 (RX)            |
| **SPI**    | 2            | 4        | RC3 (SCK), RC4 (SDI), RC5 (SDO), RB3 (SS) |
| **I2C**    | 2            | 0        | *                              |
| **PWM**    | 10           | 1        | *                              |
| **ICSP**   | 1            | 1        | RB6 (PGC), RB7 (PGD), MCLR    |


![MPlabsnap](https://github.com/user-attachments/assets/7c83ba98-b304-4525-8ae1-14bd033ae50f)


## Team Role and Responsibilities

My role as a member of this team is the **actuator**, using a **stepper motor** to create a waveform using a string. I am responsible for ensuring precise control of the motor to achieve the desired motion and vibration needed for sound generation. 

For **communication**, I use **SPI** to interface with the motor driver and **UART** to connect with my teammates' systems. I also contribute to **power management**, making sure the motor and driver receive a stable power supply. Additionally, I assist in **PCB design**, ensuring that all components are properly integrated and function efficiently within the overall system.

## Final Microcontroller Choice and Rationale

After careful consideration of multiple microcontroller options, the **PIC18F47Q10** has been chosen as the optimal microcontroller for this project. This decision is based on several key factors, including its **robust peripheral set, efficient power consumption, and strong software support**. The **PIC18F47Q10** provides essential features such as **multiple UART, SPI, and I2C channels**, making it well-suited for handling communication with both the motor driver and other system components. Additionally, it offers **flexible PWM outputs and timers**, which are crucial for precise stepper motor control. 

Another significant advantage is my **previous experience working with PIC microcontrollers**, which will expedite development and troubleshooting, allowing for a more efficient workflow. The **availability of extensive documentation and Microchip’s development tools, including MPLAB X and MCC**, further strengthens this choice. The microcontroller's **low-cost, reliable performance, and easy integration into the PCB design** make it the best fit for our project. With this selection finalized, I will ensure that we acquire the necessary hardware promptly to stay on track with our development timeline.


## 3) Power Budget
![Untitled spreadsheet - Sheet1 (1)_page-0001 (1)](https://github.com/user-attachments/assets/33cfeae8-e38f-417e-bd09-71f148c52443)



