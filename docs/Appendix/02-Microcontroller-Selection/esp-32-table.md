---
title: Appendix - Controller Table for the ESP32
---

| ESP Info                                      | Answer | Help                                                                                                      |
| --------------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------- |
| Model                                         |   ESP32-S3-WROOM-1-N4   | 
| Product Page URL                              |  ESP32-S3-WROOM-1-N4 [Product Page](https://www.espressif.com/en/products/modules/esp32-s3-wroom-1)      |  
| ESP32-S3-WROOM-1-N4 Datasheet URL             |  ESP32-S3-WROOM-1-N4 [Datasheet](https://documentation.espressif.com/esp32-s3-wroom-1_wroom-1u_datasheet_en.pdf)    |
| ESP32 S3 Datasheet URL                        | ESP32 S3 [Datasheet](https://documentation.espressif.com/esp32-s3_datasheet_en.pdf)      | 
| ESP32 S3 Technical Reference Manual URL       | ESP32 S3 [Technical Reference Manual](https://documentation.espressif.com/esp32-s3_technical_reference_manual_en.pdf)      |
| Vendor link                                   | Part can be found [here](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639)      | 
| Code Examples                                 | ?      | url(s) for libraries on github or other sites related to the microcontroller and your planned peripherals |
| External Resources URL(s)                     | ?      | Search on Google and YouTube for other resources for each specific microcontroller.                       |
| Unit cost                                     | $5.06      | Find on Digikey, Jameco, MPJA, or octopart                                                                |
| Absolute Maximum Current for entire IC        | 1.1 A      | Find in the microcontroller datasheet                                                                     |
| Supply Voltage Range                          | Min: 3.0 V
Nominal: 3.3 V
Max: 3.6 V
Absolute Max: 3.6 V      | Min / Nominal / Max / Absolute Max, as found in datasheet                                                 |
| Absolute Maximum current <br> (for entire IC) | 1.5A      | as found in datasheet                                                                                     |
| Maximum GPIO current <br> (per pin)           | 40 mA      | as found in datasheet                                                                                     |
| Supports External Interrupts?                 | Yes (on most GPIO pins)      | as found in datasheet                                                                                     |
| Required Programming Hardware, Cost, URL      | ?      | as found in datasheet                                                                                     |

| Module         | # Available | Needed | Associated Pins (or * for any) |
| -------------- | ----------- | ------ | ------------------------------ |
| UART           | 3           | ?      | ?                              |
| external SPI\* | 2           | ?      | ?                              |
| I2C            | 2           | ?      | ?                              |
| GPIO           | 45           | ?      | ?                              |
| ADC            | 20           | ?      | ?                              |
| LED PWM        | 16           | 0      | N/A                              |
| Motor PWM      | 16           | 0      | N/A                              |
| USB Programmer | 1           | 1      | ?                              |
| ...            |



\* The ESP32-S2 has multiple SPI interfaces, but some are for internal use
