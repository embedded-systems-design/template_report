## Component Selection Report

### Motor Selection
| Motor Type | Pros | Cons | Cost | Datasheet/Buy Link |
|------------|------|------|------|--------------------|
| NEMA 17 Stepper Motor | Widely used in similar projects, ample tutorials available | Not available on Digikey | $14 (x2) | [Datasheet](https://pages.pbclinear.com/rs/909-BFY-775/images/Data-Sheet-Stepper-Motor-Support.pdf) / [Buy](https://www.amazon.com/STEPPERONLINE-Stepper-Bipolar-Connector-compatible/dp/B00PNEQKC0/) |
| 324 Stepper Motor Hybrid | Available on Digikey, compatible with 12V power | Fewer online resources and tutorials | $14 (x2) | [Datasheet](https://cdn-shop.adafruit.com/product-files/324/C140-A+datasheet.jpg) / [Buy](https://www.digikey.com/en/products/detail/adafruit-industries-llc/324/5022791) |
| NEMA 23 Stepper Motor | High torque, holds position well, simple controls | Limited response time, more expensive | $31 (x2) | [Datasheet](https://cdn-shop.adafruit.com/product-files/5117/5117_Stepper_Motor_Data_Sheet.pdf) / [Buy](https://www.digikey.com/en/products/detail/adafruit-industries-llc/5117/14639999) |

## Motor Driver Selection

| Motor Driver | Pros | Cons | Cost | Datasheet/Buy Link |
|-------------|------|------|------|---------------------|
| DRV8825 Stepper Motor Driver | High current capacity (2.5A peak), Microstepping support (up to 1/32), Widely used with tutorials available | Requires heat dissipation for higher currents | ~$8 | [Datasheet](https://www.ti.com/lit/ds/symlink/drv8825.pdf) / [Buy Link](https://www.pololu.com/product/2133) |
| A4988 Stepper Motor Driver | Simple to use, Supports microstepping (up to 1/16), Affordable | Lower current limit (2A peak), Less efficient cooling | ~$5 | [Datasheet](https://www.allegromicro.com/en/products/motor-driver-ics/stepper-motor-drivers/a4988) / [Buy Link](https://www.pololu.com/product/1182) |
| TB6600 Stepper Motor Driver | High power handling (4.5A peak), Good heat dissipation, Adjustable current settings | Bulky, More expensive | ~$15 | [Datasheet](https://www.makerguides.com/tb6600-stepper-motor-driver-arduino-tutorial/) / [Buy Link](https://www.amazon.com/dp/B07G6GLVZJ) |

### Microcontroller Selection
| Microcontroller | Pros | Cons | Cost | Datasheet/Buy Link |
|-----------------|------|------|------|--------------------|
| PIC18F47Q10 | Built-in Bluetooth, supports UART | Limited SPI/I2C channels | $6 | [Datasheet](https://www.infineon.com/dgdl/Infineon-CY8C4248LQI-BL583-DataSheet-v06_00-EN.pdf?fileId=8ac78c8c7ddc01d7017e2c2187d472b7) |
| ESP32-S3-WROOM-1-N4 | Wi-Fi/Bluetooth, powerful processing | Higher power consumption | $5 | [Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-s3-wroom-1_datasheet_en.pdf) |

## Role of Team
My primary responsibility is managing the motor and motor driver, ensuring precise control over the string's motion to produce different sound waves. I am also in charge of designing and constructing the physical structure, making sure it is sturdy, functional, and integrates well with the other components. For sensing, I focus on monitoring motor position and speed, possibly using encoders or current sensing. Actuation involves selecting and implementing the appropriate motor and driver to achieve smooth and consistent movement. In terms of display, I ensure that motor status and control feedback are visible. Power management is crucial, as the motor requires stable voltage and current to function efficiently without overloading the system.

## Pick of Mircocontroller
The ESP32-S3-WROOM-1-N4 is the better choice for controlling a NEMA 17 stepper motor due to its higher processing power, built-in WiFi and Bluetooth, and strong software support. It offers flexible PWM outputs and timers for precise motor control, along with more RAM and Flash memory for expandability.

# ESP32-S3-WROOM-1-N4 Pin Allocation

## Pinout Table

| **Peripheral**   | **Pin(s)**  | **Description**                            |
|------------------|------------|--------------------------------------------|
| **Power**        | 2 (3V3)    | Main power supply (3.3V).                 |
|                  | 1 (GND)    | Ground connection.                         |
| **UART**         | 43 (GPIO43)| UART0 TXD (Transmit Data).                 |
|                  | 44 (GPIO44)| UART0 RXD (Receive Data).                 |
| **SPI**          | 36 (GPIO36)| SPI_MISO (Master In Slave Out).           |
|                  | 35 (GPIO35)| SPI_MOSI (Master Out Slave In).           |
|                  | 37 (GPIO37)| SPI_CLK (Clock).                          |
|                  | 34 (GPIO34)| SPI_CS (Chip Select).                     |
| **SPI2**         | 33 (GPIO36)| SPI_MISO (Master In Slave Out).           |
|                  | 32 (GPIO35)| SPI_MOSI (Master Out Slave In).           |
|                  | 31 (GPIO37)| SPI_CLK (Clock).                          |
|                  | 30 (GPIO34)| SPI_CS (Chip Select).                     |
| **ADC**          | 1 (GPIO1)  | ADC1 Channel 0.                            |
| **DAC**          | 17 (GPIO17)| DAC1 output.                               |
| **PWM**          | 2 (GPIO2)  | PWM output                               |
| **GPIO**         | 3 (GPIO3)  | General-purpose input/output (Buttons, LEDs). |

## Final Pin Count Estimation

| **Category**             | **Estimated Pins** |
|-------------------------|-------------------|
| **SPI** (MOSI, MISO, CLK, CS) | 8 |
| **UART (TX, RX)**       | 2 |
| **Power (3.3V, GND x2)** | 3 |
| **Motor Driver (DIR, STEP, EN)** | 3 |
| **ADC (Optional)**       | 1 |
| **DAC (Optional)**       | 1 |
| **PWM (LEDs, Motor Speed)** | 1 |
| **GPIO (Buttons, Indicators)** | 2 |
| **Programming & Debugging** | 2–4 |


## Reference
For more details, check the [ESP32-S3-WROOM-1 datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-s3-wroom-1_wroom-1u_datasheet_en.pdf).


### Power Supply & Regulation
| Component | Pros | Cons | Cost | Datasheet/Buy Link |
|-----------|------|------|------|--------------------|
| LM7805 (5V Regulator) | Simple, widely available | Inefficient linear regulator | $1 | [Datasheet](https://www.ti.com/lit/ds/symlink/lm7805.pdf) |
| MP1584 (Switching Regulator) | High efficiency, adjustable voltage | Requires external components | $3 | [Datasheet](https://www.monolithicpower.com/en/documentview/productdocument/index/version/2/document_type/Datasheet/lang/en/sku/MP1584) |

### Rationale for Selections
- **Motor Selection:** NEMA 17 is chosen due to extensive documentation, ease of programming, and cost-effectiveness.
- **DRV8825 Stepper Motor Driver:**  
- **Microcontroller:** ESP32-S3 is selected due to its strong wireless capabilities and sufficient GPIOs for the project.
- **Sensor:** BNO085 is optimal due to its accuracy and built-in fusion algorithms, reducing processing overhead.
- **Power Regulation:** MP1584 is chosen for efficiency in voltage regulation, ensuring stable operation.

---

