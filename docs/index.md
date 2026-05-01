---
title: Welcome
tags:
- tag1
- tag2
---
<center>
<font size= "6">Arianna Lazaritt's Datasheet</font><br>
as part of<br>
<font size= "8"> Rover Project</font><br>
for<br>
<font size= "5"> Team 305 </font><br>

**Submission: May 4, 2026**
</center>

## Introduction

This datasheet provides an overview of the camera imaging board, a key component within my team's rover system, explaining its design, functionality, and integration within the overall project. It includes a block diagram illustrating how the camera, microcontroller, and other hardware pieces interact to capture video image, and explanations of module requirements, component selection, the circuit schematic and PCB, the board’s power budget, and all code used to run it. This document should serve as a technical reference and provide a clear understanding of the board’s operation and its contribution to my team’s overall project.

### Project Summary

Our team is developing an investigative rover to model how autonomous or remotely operated systems could perform environmental observations on planetary terrains. The system is organized into various specialized subsystems that work together to support exploration and monitoring.

The subsystems communicate through a UART-based daisy-chain network that allows boards to pass data and status messages between one another. This structure enables the rover to relay telemetry to a base station or local display while coordinating the operation of the different modules.
More details on project requirements, user needs, and other aspects of the overall system can be found in the [team report.](https://egr314-s-2026-30.github.io/EGR314-S-2026-305.github.io/)

### My Contribution

My contribution to the system is the imaging subsystem. This board integrates a camera module that captures images from the rover’s field of view and sends out the corresponding data packets. This enables users to monitor the environment and observe navigation and observation while the rover is in use.

A microcontroller on the board manages camera configuration and communication, ensuring proper operation of the camera while interfacing with the rest of the rover’s network. The microcontroller also relays messages and data between other subsystem boards as part of the rover’s UART daisy-chain communication.

Although the board was originally designed specifically for camera functionality, its use was later extended by integrating a rotary encoder through extra available GPIO pins. This addition allowed the subsystem to support manual user input, enhancing interactivity and demonstrating the flexibility of the design beyond its initial scope.



To see functions and prioritization of goals within the subsytem, see the [Requirements](https://alazaritt.github.io/EGR314DataSheet/01-Requirements/Requirements/) section

To see how all components within the subsytem communicate and interact, see the [Block Diagram](https://alazaritt.github.io/EGR314DataSheet/02-Block-Diagram/Block-Diagram/) section of the datasheet.

For additional reasoning of why individual components were selected, please see the [Component selection](https://alazaritt.github.io/EGR314DataSheet/03-Component-Selection/Component-Selection/) section of the datasheet.

To review the details listed of the components and hardware used, see the [BOM](https://alazaritt.github.io/EGR314DataSheet/04-BOM/BOM/) section of the datasheet.

For a more in depth overview of the subsystem and to access associated files with it, review the [Schematic](https://alazaritt.github.io/EGR314DataSheet/05-Schematic/schematic/) section of the datasheet.

To see how power was taken into consideration and a calulated current draw of all components within the system, see the [Power Budget](https://alazaritt.github.io/EGR314DataSheet/Appendix/03-Power-Budget/Power-Budget/) section of the datasheet.

Images and renders of my PCB can be found in the [PCB](https://alazaritt.github.io/EGR314DataSheet/06-PCB/pcb/) section.

My portion of the team's API message structure can be found [here](https://alazaritt.github.io/EGR314DataSheet/07-API/API/)

Ideas of hardware improvements and adjustments are documented under [Hardware V2.0](https://alazaritt.github.io/EGR314DataSheet/08-Hardware%20V2.0/Hardware%20V2.0/)

The code that wwas used to run the subsytem can be found in the [Resources](https://alazaritt.github.io/EGR314DataSheet/09-Resources/Resources/) part of the datasheet. 

All other supporting information is located in the [appendix](https://alazaritt.github.io/EGR314DataSheet/Appendix/)
