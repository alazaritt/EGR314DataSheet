---
title: Appendix - Power Budget
---

## Overview
This power budget was created to verify that the selected power source and voltage regulation scheme can reliably supply all major components in the system under worst-case operating conditions. The power budget accounts for the absolute maximum current consumption of each active component, the ESP32-S3 microcontroller and the OV2640 camera module, based on manufacturer datasheets and known operating conditions. A 25% safety margin was applied to the total system current to account for possible current surges, component tolerances, and future design expansion. Developing this power budget helps prevent undervaluing current requirements, reduces the risk of unstable operation, and ensures that the selected regulators and power sources are appropriately sized for the final system.

![budget1](https://github.com/alazaritt/EGR314DataSheet/blob/main/docs/Appendix/03-Power-Budget/Power%20Budget%20ss.png?raw=true)

## Conclusions

From the prepared power budget, it was determined that the system requires a maximum of 1.5 A at 3.3 V when all subsystems are operating simultaneously, including accounting for peak Wi-Fi transmission on the microcontroller and active image capture by the camera. With the inclusion of a 25% safety margin, the selected 3.3 V regulator and 9 V external power source provide sufficient current headroom to ensure stable operation without overheating or voltage drop. The analysis confirms that the chosen power hardware is capable of supporting worst-case operating conditions and allows for minor future expansions without requiring changes to the power subsystem. Overall, the power budget validates that the current power design is safe, robust, and appropriate for the intended application.
## Resouces

The power budget as a PDF download is available [*here*](https://github.com/alazaritt/EGR314DataSheet/releases/download/powerbudget/Power.Budget.Example.pdf), and a Microsoft Excel Sheet [*here*](https://github.com/alazaritt/EGR314DataSheet/releases/download/powerbudget/Power.Budget.Example.xlsx).
