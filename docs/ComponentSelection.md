## Component Selection Report

### Motor Selection
| Motor Type | Pros | Cons | Cost | Datasheet/Buy Link |
|------------|------|------|------|--------------------|
| NEMA 17 Stepper Motor | Widely used in similar projects, ample tutorials available | Not available on Digikey | $14 (x2) | [Datasheet](https://pages.pbclinear.com/rs/909-BFY-775/images/Data-Sheet-Stepper-Motor-Support.pdf) / [Buy](https://www.amazon.com/STEPPERONLINE-Stepper-Bipolar-Connector-compatible/dp/B00PNEQKC0/) |
| 324 Stepper Motor Hybrid | Available on Digikey, compatible with 12V power | Fewer online resources and tutorials | $14 (x2) | [Datasheet](https://cdn-shop.adafruit.com/product-files/324/C140-A+datasheet.jpg) / [Buy](https://www.digikey.com/en/products/detail/adafruit-industries-llc/324/5022791) |
| NEMA 23 Stepper Motor | High torque, holds position well, simple controls | Limited response time, more expensive | $31 (x2) | [Datasheet](https://cdn-shop.adafruit.com/product-files/5117/5117_Stepper_Motor_Data_Sheet.pdf) / [Buy](https://www.digikey.com/en/products/detail/adafruit-industries-llc/5117/14639999) |

### Microcontroller Selection
| Microcontroller | Pros | Cons | Cost | Datasheet/Buy Link |
|-----------------|------|------|------|--------------------|
| CY8C4248LYI-BL583 | Built-in Bluetooth, supports UART | Limited SPI/I2C channels | $6 | [Datasheet](https://www.infineon.com/dgdl/Infineon-CY8C4248LQI-BL583-DataSheet-v06_00-EN.pdf?fileId=8ac78c8c7ddc01d7017e2c2187d472b7) |
| ESP32-S3-WROOM-1-N4 | Wi-Fi/Bluetooth, powerful processing | Higher power consumption | $5 | [Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-s3-wroom-1_datasheet_en.pdf) |

### Sensor Selection
| Sensor | Pros | Cons | Cost | Datasheet/Buy Link |
|--------|------|------|------|--------------------|
| MPU6050 (IMU) | Popular, widely documented, I2C support | Older model, lower precision | $4 | [Datasheet](https://www.invensense.com/wp-content/uploads/2015/02/MPU-6000-Datasheet1.pdf) |
| BNO085 (IMU) | High accuracy, fusion algorithms built-in | More expensive, limited availability | $10 | [Datasheet](https://www.ceva-dsp.com/wp-content/uploads/2019/07/BNO080_BNO085_Datasheet_v1.4.pdf) |

### Power Supply & Regulation
| Component | Pros | Cons | Cost | Datasheet/Buy Link |
|-----------|------|------|------|--------------------|
| LM7805 (5V Regulator) | Simple, widely available | Inefficient linear regulator | $1 | [Datasheet](https://www.ti.com/lit/ds/symlink/lm7805.pdf) |
| MP1584 (Switching Regulator) | High efficiency, adjustable voltage | Requires external components | $3 | [Datasheet](https://www.monolithicpower.com/en/documentview/productdocument/index/version/2/document_type/Datasheet/lang/en/sku/MP1584) |

### Rationale for Selections
- **Motor Selection:** NEMA 17 is chosen due to extensive documentation, ease of programming, and cost-effectiveness.
- **Microcontroller:** ESP32-S3 is selected due to its strong wireless capabilities and sufficient GPIOs for the project.
- **Sensor:** BNO085 is optimal due to its accuracy and built-in fusion algorithms, reducing processing overhead.
- **Power Regulation:** MP1584 is chosen for efficiency in voltage regulation, ensuring stable operation.

---

