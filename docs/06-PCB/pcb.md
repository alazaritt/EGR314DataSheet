---
title: Module's PCB
---

## PCB
My PBC is responsible for handling all configuration and communication of the camera system for my team’s rover. It uses an ESP-32 to handle all communication, as well as an OV2460 camera to capture video to be wirelessly transmitted and streamed to a separate user interface. It also has a USB connector that is used to program the ESP-32. The PCB layout ensures that all components are properly placed for minimal noise, and that all power and ground connections are strong enough for reliable signal transmission

In order to safely carry current, all power traces are 40 mils, which helps to reduce voltage drops. All other signal traces, like those connecting the camera, USB, ribbon cables, voltage regulator, microcontroller I/O pins, and other additional hardware are 15 mils, which is sufficient for lower current signals. Bypass and decoupling capacitors have been used throughout the PCB with shorter traces to reduce noise. This design ensures reliable communication and use of imaging components while maintaining manufacturability and signal strength.
