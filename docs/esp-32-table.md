---
title: ESP32 Table
---

| ESP Info                                      | Answer | Help                                                                                                      |
| --------------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------- |
| Model                                         | 1965-ESP32-S3-WROOM-1-N4      | Include the entire part number (leave off any letters at the end that specify the package type)           |
| Product Page URL                              | [link](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639)      | Found on Espressif.com                                                                                    |
| ESP32-S3-WROOM-1-N4 Datasheet URL             | [Link](https://www.espressif.com/sites/default/files/documentation/esp32-s3-wroom-1_wroom-1u_datasheet_en.pdf)      | Do not paste links directly into the table.  Use a [link](#)                                              |
| ESP32 S3 Datasheet URL                        | [link](https://www.espressif.com/sites/default/files/documentation/esp32-s3_datasheet_en.pdf)     | Has more detail on functions                                                                              |
| ESP32 S3 Technical Reference Manual URL       | n/a      | Has details on I/O multiplexing, USB, and others                                                          |
| Vendor link                                   | [link](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639)      | Digikey, Jameco, etc.  Do not paste links directly into the table.  Use a [link](#)                       |
| Code Examples                                 | n/a     | url(s) for libraries on github or other sites related to the microcontroller and your planned peripherals |
| External Resources URL(s)                     | n/a     | Search on Google and YouTube for other resources for each specific microcontroller.                       |
| Unit cost                                     | $2.95      | Find on Digikey, Jameco, MPJA, or octopart                                                                |
| Absolute Maximum Current for entire IC        | 95Ma      | Find in the microcontroller datasheet                                                                     |
| Supply Voltage Range                          | 3.6V     | Min / Nominal / Max / Absolute Max, as found in datasheet                                                 |
| Absolute Maximum current <br> (for entire IC) | 97Ma     | as found in datasheet                                                                                     |
| Maximum GPIO current <br> (per pin)           | 8      | as found in datasheet                                                                                     |
| Supports External Interrupts?                 | yes      | as found in datasheet                                                                                     |
| Required Programming Hardware, Cost, URL      | [link](https://docs.espressif.com/projects/esp-idf/en/latest/esp32s3/get-started/index.html)     | as found in datasheet                                                                                     |

| Module         | # Available | Needed | Associated Pins (or * for any) |
| -------------- | ----------- | ------ | ------------------------------ |
| UART           | 33          | 2      | all IO pins                    |
| external SPI\* | 33           | 0      | all IO pins                   |
| I2C            | 33           | 0      | all IO pins                   |
| GPIO           | 33           | 1      | IO3                           |
| ADC            | 33           | 0      | all IO pins                   |
| LED PWM        | 33           | 0      | all IO pins                   |
| Motor PWM      | 33           | 0      | all IO pins                   |
| USB Programmer | 2            | 2      | IO19/IO20                     |
| ...            |



\* The ESP32-S2 has multiple SPI interfaces, but some are for internal use


## esp32 pinout

![Alternative Image](https://github.com/user-attachments/assets/c0f0fe39-41e3-40be-8dc0-98fd614f0806)


