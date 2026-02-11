---
title: Appendix - Controller Table for the ESP32
---

| ESP Info                                      | Answer                                                                                                    |
| --------------------------------------------- | ------ |
| Model                                         |   ESP32-S3-WROOM-1-N4   | 
| Product Page URL                              |  ESP32-S3-WROOM-1-N4 [Product Page](https://www.espressif.com/en/products/modules/esp32-s3-wroom-1)      |  
| ESP32-S3-WROOM-1-N4 Datasheet URL             |  ESP32-S3-WROOM-1-N4 [Datasheet](https://documentation.espressif.com/esp32-s3-wroom-1_wroom-1u_datasheet_en.pdf)    |
| ESP32 S3 Datasheet URL                        | ESP32 S3 [Datasheet](https://documentation.espressif.com/esp32-s3_datasheet_en.pdf)      | 
| ESP32 S3 Technical Reference Manual URL       | ESP32 S3 [Technical Reference Manual](https://documentation.espressif.com/esp32-s3_technical_reference_manual_en.pdf)      |
| Vendor link                                   | Part can be found [here](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639)      | 
| Code Examples                                 | The following repositories contain references and examples for camera use and SPI communication [1](https://github.com/espressif/esp-idf/tree/master/examples) [2](https://github.com/espressif/esp32-camera)      |
| External Resources URL(s)                     | This [video](https://www.youtube.com/watch?v=G6MROvlLeKE) shows how to use a camera with an ESP32 as well as this [website](https://how2electronics.com/interfacing-5mp-spi-camera-with-esp32-wifi-module/)     | 
| Unit cost                                     | $5.06      | 
| Absolute Maximum Current for entire IC        | 1.1 A      | 
| Supply Voltage Range                          | Min: 3.0 V <br>Nominal: 3.3 V<br>Max: 3.6 V<br>Absolute Max: 3.6 V      | 
| Absolute Maximum current <br> (for entire IC) | 1.5A      | 
| Maximum GPIO current <br> (per pin)           | 40 mA      | 
| Supports External Interrupts?                 | Yes (on most GPIO pins)      | 
| Required Programming Hardware, Cost, URL      | USB cable <br>Cost: $3.67<br>  [URL](https://www.digikey.com/en/products/detail/sparkfun-electronics/24508/22321088?gclsrc=aw.ds&gad_source=1&gad_campaignid=20243136172&gbraid=0AAAAADrbLlh1Tbp4mMm-KRkdY0tp4aE4j&gclid=Cj0KCQiAy6vMBhDCARIsAK8rOglMUt9YNMxXbo9cCV_Mz9d8SoXXu6UsXyn7V7zAz9T4bsDBuVud988aAuN6EALw_wcB)   |                                                                                 

| Module         | # Available | Needed | Associated Pins (or * for any) |
| -------------- | ----------- | ------ | ------------------------------ |
| UART           | 3           | 2      | GPIO 43 (TX), GPIO 44 (RX)                              |
| external SPI\* | 2           | 0      | N/A                              |
| I2C            | 2           | 2      | GPIO 8 (SDA), GPIO 9 (SCL)                              |
| GPIO           | 45           | 15      | GPIO 5–16, others flexible                              |
| ADC            | 20           | 0      | N/A                              |
| LED PWM        | 16           | 0      | N/A                              |
| Motor PWM      | 16           | 0      | N/A                              |
| USB Programmer | 1           | 1      | GPIO 19 (V−), GPIO 20 (V+)                              |



\* The ESP32-S2 has multiple SPI interfaces, but some are for internal use


My role on the team is responsible for the imaging and embedded processing subsystem. This includes interfacing with the camera module, configuring and controlling the camera via a serial control interface, capturing image data, and handling communication with other team subsystems via UART. I am also responsible for allocating GPIO resources and ensuring proper power delivery to the camera and microcontroller No high-power actuation is controlled directly by this subsystem, but GPIO pins are reserved for indicators and future expansion if needed.

The ESP32-S3-WROOM-1-N4 module was selected as the primary microcontroller for this subsystem. This module integrates the ESP32-S3 dual-core processor, onboard flash memory, and RF components into a surface-mount module that is compatible with hand-assembled PCBs while avoiding direct soldering of fine-pitch BGA devices.

