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

### Actuator

(**remove this note/placeholder**: if applicable, this is where your **Selected** the actuator items go, which includes both the driver and motor. Otherwise, remove this section.)

For more details, review the ["Appendix - Component Selection Process - Actuator"](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/Appendix/01-Componet-Selection/Component-Selection-Process/#actuator) selection.

-----------

*Table 1: Example component selection*

**External Clock Module**

| **Component**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/6286/150%7EC04-034%7EAB%7E3.jpg?hidebanner=true)<br> TC1264-3.3VAB<br>$1.33/each<br>[link to product](https://www.digikey.com/en/products/detail/microchip-technology/TC1264-3.3VAB/442615?gclsrc=aw.ds&gad_source=1&gad_campaignid=20790518593&gbraid=0AAAAADrbLli0ZT-PF-PBunQ9vVqrEbgw6&gclid=CjwKCAiAqKbMBhBmEiwAZ3UboBYWfaOkWoOk2i8Dx9zRFfUYjNxC4Bj-PdhP4Dzw3kDAWWd71TOCJxoCmtIQAvD_BwE)                 | \* High output capacity<br>\* Built in protection for over-current and temperature<br>\* Wide Operating Range                                               | \* High Dropout Voltage<br>\* Inefficient for power sensitive designs<br>\* Difficult with non-through hole designs |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/010/103/MFG_AP6320x_sml.jpg)<br> AP63203WU-7 IC 3.3V 2A TSOT23-6<br>$0.77/each<br>[link to product](https://www.digikey.com/en/products/detail/diodes-incorporated/AP63203WU-7/9858430?)                 | \* Inexpensive<br>\* Compact SMT Package<br>\* Wide Input Voltage Range                                               | \* Requires external components <br>\* Layout Sensitive<br>\*Poor heat dissipation at high Vin. |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/6310/488%7E314D-04%7ET%2CTQ%7E5.jpg?hidebanner=true)<br> LM2575T-3.3G<br>$2.51/each<br>[link to product](https://www.digikey.com/en/products/detail/diodes-incorporated/AP63203WU-7/9858430?)                 | \* Wide Input Voltage Range<br>\* Simple external components<br>\* Efficient switching design                                               | \* More expensive <br>\* Not surface mount<br>\*Lower switching frequency |

**Choice:** Option 3: LM2575T‑3.3V switching regulator
**Rationale:** The LM2575T‑3.3G is a simple and reliable 3.3 V regulator that can deliver up to 1 A from a wide input range (4.75–40 V). Its switching design is more efficient than linear regulators, reducing heat when stepping down from higher voltages. It is reliable and shold be easy to implement and integrate into circuits.

