---
title: Module's Selected Major Components
---

## Module's Selected Major Components

The following sections are the selected major components necessary for  .....

>**For each of the following sections, use <ins>one of the two styles</ins> given near the end. *REMOVE THIS NOTE***

### Power Management

(**remove this note/placeholder**: this is where your 3.3 volt switching regulator, any other needed power regulator, and power source {if applicable} **THAT WERE SELECTED**)

For more details, review the ["Appendix - Component Selection Process - Power Mangement"](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/Appendix/01-Componet-Selection/Component-Selection-Process/#power-management) selection.

### Sensor

(**remove this note/placeholder**: if applicable, this is where your  **SELECTED** sensor is shown. Otherwise, remove this section.)

For more details, review the ["Appendix - Component Selection Process - Sensor"](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/Appendix/01-Componet-Selection/Component-Selection-Process/#sensor) selection.



-----------

*Table 1: Component selection*

**Voltage Regulator**

| **Component**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/6286/150%7EC04-034%7EAB%7E3.jpg?hidebanner=true)<br> TC1264-3.3VAB<br>$1.33/each<br>[link to product](https://www.digikey.com/en/products/detail/microchip-technology/TC1264-3.3VAB/442615?gclsrc=aw.ds&gad_source=1&gad_campaignid=20790518593&gbraid=0AAAAADrbLli0ZT-PF-PBunQ9vVqrEbgw6&gclid=CjwKCAiAqKbMBhBmEiwAZ3UboBYWfaOkWoOk2i8Dx9zRFfUYjNxC4Bj-PdhP4Dzw3kDAWWd71TOCJxoCmtIQAvD_BwE)                 | \* High output capacity<br>\* Built in protection for over-current and temperature<br>\* Wide Operating Range                                               | \* High Dropout Voltage<br>\* Inefficient for power sensitive designs<br>\* Difficult with non-through hole designs |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/010/103/MFG_AP6320x_sml.jpg)<br> AP63203WU-7 IC 3.3V 2A TSOT23-6<br>$0.77/each<br>[link to product](https://www.digikey.com/en/products/detail/diodes-incorporated/AP63203WU-7/9858430?)                 | \* Inexpensive<br>\* Compact SMT Package<br>\* Wide Input Voltage Range                                               | \* Requires external components <br>\* Layout Sensitive<br>\*Poor heat dissipation at high Vin. |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/001/202/815/296%7E4202506%7EDCY%7E4_sml%28200x200%29.jpg)<br> TLV76133DCYR<br>$0.48/each<br>[link to product](https://www.digikey.com/en/products/detail/texas-instruments/TLV76133DCYR/18716969?gclsrc=aw.ds&gad_source=1&gad_campaignid=20228387720&gbraid=0AAAAADrbLljWmZW5sdxv23XwNjtDfhxpY&gclid=Cj0KCQiAy6vMBhDCARIsAK8rOgnRhcYEEiF5ic2ROonZhhoX9dVTQM1dgRZhIbySp399Z6YhaxasOxwaAvqYEALw_wcB)                 | \* High current capability<br>\* Good output accuracy<br>\* Wide Input Voltage Range                                               | \* Moderate dropout voltage <br>\*Poor heat dissipation at high Vin. |

**Choice:** Option 3: TLV76133DCYR 3.3V switching regulator
**Rationale:** The TLV76133DCYR provides a stable and accurate 3.3 V output with  little design complexity. It can handle up to 1 A and  works over a wide input voltage range, fitting well with the available supply. It requires only small ceramic capacitors and includes built-in protection features, which helps keep the PCB simple, compact, and reliable.

**Camera**

| **Component**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](https://www.arducam.com/media/catalog/product/cache/45336f8944e7eb3ec4b20e42d64c20ed/a/r/arducam-_ov2640_-camera_module_m0031-1.jpg)<br> OV2640 2MP Camera Module<br>$6.99/each<br>[link to product](https://www.arducam.com/arducam-ov2640-camera-module-2mp-mini-ccm-compact-camera-modules-compatible-with-arduino_m0031esp32-esp8266-development-board-with-dvp-24-pin-interface_.html)                 | \* Good 2MP resolution<br>\* On‑chip JPEG compression<br>\* Easily compatible with ESP32 modules                                               | \* Not ideal for high resolution images<br>\* Fixed focus<br>\* Requires careful wiring to reduce noise |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/002/138/725/MFG_B0400_sml.jpg)<br> OV5640 5 MP<br>$40.92/each<br>[link to product](https://www.digikey.com/en/products/detail/arducam/B0400/19116509?gclsrc=aw.ds&gad_source=1&gad_campaignid=20232005509&gbraid=0AAAAADrbLlj1fnVHDFXcm9ZQE3CLO1GPB&gclid=Cj0KCQiAy6vMBhDCARIsAK8rOglpbaWs6xKmgRJQkk2K2B5ids20uMjPOvCeqMobiPXRw5iLrOl5xi8aAojIEALw_wcB)                 | \* Easy to implement with ESP32<br>\* Moderate resolution<br>\* Supports autofocus                                               | \* Idle power consumption <br>\* May require complex software integration |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/003/220/197/CAMERA-OV7670_sml%28200x200%29.jpg)<br> CAMERA-OV7670<br>$5.92/each<br>[link to product](https://www.digikey.com/en/products/detail/olimex-ltd/CAMERA-OV7670/21662189?gclsrc=aw.ds&gad_source=1&gad_campaignid=23410779255&gbraid=0AAAAADrbLlhlt3SD16S1QgVRKgIqMNvJu&gclid=Cj0KCQiAy6vMBhDCARIsAK8rOglJn91DAUynbqBVx4kB63ikL1yjSF6BrEwIhMDMANKIyLXUkxM-Wd4aAs5aEALw_wcB)                 | \* Inexpensive <br>\* Less processing needed                                               | \* Low resolution <br>\*Complex wiring required<br>\*Low frame rates |

**Choice:** Option 1: OV2640 camera
**Rationale:** The ESP32-CAM OV2640 provides a good balance of resolution, ease of use, and ESP32 support, to quickly capture images and stream video without extra hardware. Its built-in library support and low cost make it ideal for rapid prototyping and embedded camera projects.


