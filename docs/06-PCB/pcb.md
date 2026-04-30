---
title: Module's PCB
---

## PCB
My PBC was designed to handle all configuration and communication of the camera system for my team’s rover. It uses an ESP-32 to handle all communication, as well as an OV2460 camera to capture video to be wirelessly transmitted and streamed to a separate user interface. It also has a USB connector that is used to program the ESP-32. The PCB layout ensures that all components are properly placed for minimal noise, and that all power and ground connections are strong enough for reliable signal transmission. It has extra open pins that were eventually used for the rotary encoder.

In order to safely carry current, all power traces are 40 mils, which helps to reduce voltage drops. All other signal traces, like those connecting the camera, USB, ribbon cables, voltage regulator, microcontroller I/O pins, and other additional hardware are 15 mils, which is sufficient for lower current signals. Bypass and decoupling capacitors, as well as pull up resistors have been used throughout the PCB with shorter traces to reduce noise. This design ensures reliable communication and use of imaging components while maintaining manufacturability and signal strength.

## Final PCB (assembled)

Front Image

![image1](https://github.com/alazaritt/EGR314DataSheet/blob/main/docs/06-PCB/pfUntitled522_20260429151009.jpg?raw=true)


Back Image

<img src="https://github.com/alazaritt/EGR314DataSheet/blob/main/docs/06-PCB/pbUntitled522_20260429144440.jpg?raw=true" 
     width="630" 
     alt="image2">

## Preassembled PCB

Front Image

![image 3](https://github.com/alazaritt/EGR314DataSheet/blob/main/docs/06-PCB/efIMG_4166.jpg?raw=true)

Back Image

![image4](https://github.com/alazaritt/EGR314DataSheet/blob/main/docs/06-PCB/ebIMG_4167.jpg?raw=true)

## From KiCad

Front Image

<img src="https://github.com/alazaritt/EGR314DataSheet/blob/main/docs/06-PCB/ecadfv.png?raw=true" 
     width="630" 
     alt="image5">

Back Image

<img src="https://github.com/alazaritt/EGR314DataSheet/blob/main/docs/06-PCB/bvecad.png?raw=true" 
     width="630" 
     alt="image5">


A zip file of my ECAD project can be found [here](https://github.com/alazaritt/EGR314DataSheet/releases/download/pcb/individual.subsystem.314.zip) and all gerber files used can be found [here](https://github.com/alazaritt/EGR314DataSheet/releases/download/pcb/camera.gerber.files.zip)
