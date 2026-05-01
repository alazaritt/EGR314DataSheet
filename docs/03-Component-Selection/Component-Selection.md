---
title: Module's Selected Major Components
---

## Module's Selected Major Components

The following sections are the selected major components necessary for the imaging subsystem. These components include the voltage regulation hardware required to provide a stable 3.3 V power rail and the camera module used for image capture. Each component was selected based on its electrical compatibility with the ESP32-based system, its ability to meet worst-case power and performance requirements, and its use in similar embedded imaging applications. Together, these components ensure reliable operation of the system while minimizing power consumption, design complexity, and integration risk.

### Power Management

**Selected Power Management Hardware: AP63203WU-7 IC 3.3V 2A regulator**

<img src="https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/010/103/MFG_AP6320x_sml.jpg" 
     width="300" 
     alt="Product Image">


[link](https://www.digikey.com/en/products/detail/diodes-incorporated/AP63203WU-7/9858430?)


### Sensor

**Selected Sensor:  OV2640 2MP Camera Module**

<img src="https://www.waveshare.com/media/catalog/product/cache/1/image/560x560/9df78eab33525d08d6e5fb8d27136e95/o/v/ov2640-camera-board_l_1_5.jpg" 
     width="300" 
     alt="Product Image">


 [link](https://spotpear.com/index/product/detail/id/260.html)  



-----------

*Table 1: Component Selection - Voltage Regulator*

**Voltage Regulator**

| **Component**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/6286/150%7EC04-034%7EAB%7E3.jpg?hidebanner=true)<br> TC1264-3.3VAB<br>$1.33/each<br>[link to product](https://www.digikey.com/en/products/detail/microchip-technology/TC1264-3.3VAB/442615?gclsrc=aw.ds&gad_source=1&gad_campaignid=20790518593&gbraid=0AAAAADrbLli0ZT-PF-PBunQ9vVqrEbgw6&gclid=CjwKCAiAqKbMBhBmEiwAZ3UboBYWfaOkWoOk2i8Dx9zRFfUYjNxC4Bj-PdhP4Dzw3kDAWWd71TOCJxoCmtIQAvD_BwE)                 | \* High output capacity<br>\* Built in protection for over-current and temperature<br>\* Wide Operating Range                                               | \* High Dropout Voltage<br>\* Inefficient for power sensitive designs<br>\* Difficult with non-through hole designs |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/010/103/MFG_AP6320x_sml.jpg)<br> AP63203WU-7 IC 3.3V 2A TSOT23-6<br>$0.77/each<br>[link to product](https://www.digikey.com/en/products/detail/diodes-incorporated/AP63203WU-7/9858430?)                 | \* Inexpensive<br>\* Compact SMT Package<br>\* Wide Input Voltage Range                                               | \* Requires external components <br>\* Layout Sensitive<br>\*Poor heat dissipation at high Vin. |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/6311/846%7EHRP5%7E%7E5.jpg?hidebanner=true)<br> BA33DD0WHFP-TR<br>$2.72/each<br>[link to product](https://www.digikey.com/en/products/detail/rohm-semiconductor/BA33DD0WHFP-TR/3663736)                 | \* High current capability<br>\* Clean output <br>\* Wide Input Voltage Range                                               | \* Lower efficiency <br>\*Poor heat dissipation. |

**Choice:** Option 2: AP63203WU-7 IC 3.3V 2A regulator

**Rationale:** The AP63203WU-7 is a 3.3 V regulator capable of handling up to 2 A and works over a wide input voltage range, while providing clean, low-noise output. Though it requires some external circutry, it remains compact, and it also includes built-in protection features to ensure reliablity.


*Table 2: Component Selection - Camera*

| **Component**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](https://www.waveshare.com/media/catalog/product/cache/1/image/560x560/9df78eab33525d08d6e5fb8d27136e95/o/v/ov2640-camera-board_l_1_5.jpg) <br> OV2640 2MP Camera Module<br>$12.89/each<br>[link to product](https://spotpear.com/index/product/detail/id/260.html)                 | \* Good 2MP resolution<br>\* On‑chip JPEG compression<br>\* Easily compatible with ESP32 modules                                               | \* Not ideal for high resolution images<br>\* Fixed focus<br>\* Requires careful wiring to reduce noise |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/002/138/725/MFG_B0400_sml.jpg)<br> OV5640 5 MP<br>$40.92/each<br>[link to product](https://www.digikey.com/en/products/detail/arducam/B0400/19116509?gclsrc=aw.ds&gad_source=1&gad_campaignid=20232005509&gbraid=0AAAAADrbLlj1fnVHDFXcm9ZQE3CLO1GPB&gclid=Cj0KCQiAy6vMBhDCARIsAK8rOglpbaWs6xKmgRJQkk2K2B5ids20uMjPOvCeqMobiPXRw5iLrOl5xi8aAojIEALw_wcB)                 | \* Easy to implement with ESP32<br>\* Moderate resolution<br>\* Supports autofocus                                               | \* Idle power consumption <br>\* May require complex software integration |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/003/220/197/CAMERA-OV7670_sml%28200x200%29.jpg)<br> CAMERA-OV7670<br>$5.92/each<br>[link to product](https://www.digikey.com/en/products/detail/olimex-ltd/CAMERA-OV7670/21662189?gclsrc=aw.ds&gad_source=1&gad_campaignid=23410779255&gbraid=0AAAAADrbLlhlt3SD16S1QgVRKgIqMNvJu&gclid=Cj0KCQiAy6vMBhDCARIsAK8rOglJn91DAUynbqBVx4kB63ikL1yjSF6BrEwIhMDMANKIyLXUkxM-Wd4aAs5aEALw_wcB)                 | \* Inexpensive <br>\* Less processing needed                                               | \* Low resolution <br>\*Complex wiring required<br>\*Low frame rates |

**Choice:** Option 1: OV2640 camera

**Rationale:** The OV2640 camera provides a good balance of resolution, ease of use, and ESP32 support, to quickly capture images and stream video without too much extra hardware. Its built-in library support and low cost make it ideal for rapid prototyping and embedded camera projects.


It was selected because it meets the subsystem’s imaging requirements while integrating easily with the ESP32 microcontroller used in the design. It supports up to 2 MP resolution and includes built-in JPEG compression, allowing for efficient image capture and transmission over Wi-Fi without additional processing hardware. This enables reliable image capture, low-resolution video streaming, and efficient packetization. Its software support, low cost, and ease of use use with ESP32 systems make it well suited for this subsystem.



*Table 3: Final Components Selected (summary)*

| **Part Name/Description** | **Manufacturer/Part Number** |
|:--------------------|:---------------|
Voltage regulator |Diodes Incorporated/AP63203WU-7  | 
Camera | OmniVision/OV2640 |
Rotary Encoder | KY-040 |

The camera subsystem did not work as originally intended, as it could only capture still images and transmit raw data packets rather than support continuous video streaming or reconstruct the image on the receiving end. To demonstrate system functionality due to this limitation, a rotary encoder was later integrated using available pins to provide a reliable form of user input and interaction. Since this component was already on hand, no in depth component selection occured for it


*Table 4: ESP32 S3 Pinout*

| **Component** | **Pin** | 
|:--------------------|:----|
Enable button | EN |
Camera | IO4 | 
Camera | IO5 |
Camera | IO6 | 
Camera | IO7 | 
Camera | IO15 | 
Camera | IO16 | 
Camera | IO17 | 
Camera | IO18 | 
Camera | IO8 |
USB D- | IO19 | 
USB D+ | IO20 | 
Camera | IO3 | 
Camera | IO46 | 
Camera | IO9 | 
Camera | IO10 |
Camera | IO11 | 
Camera | IO12 |
Rotary encoder SW | IO13 | 
Rotary encoder DT | IO14 | 
Rotary encoder CLK | IO21 | 
Extra open pin | IO47 | 
Boot button | IO0 | 
Reset button | IO35 | 
LED | IO36 | 
UART TX | IO43 | 
UART RX | IO44 | 
