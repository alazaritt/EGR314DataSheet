---
title: Module Schematic
---

## Overview

This schematic is designed to support the imaging subsystem by integrating the ESP32-S3 microcontroller with the OV2640 camera to capture and process image data, along with a rotary encoder added for user input functionality. The ESP32 microcontroller configures the camera through an I2C interface and receives pixel data through dedicated data and clock lines, allowing for image capture, packetized data transfer and camera status updates. Collected data is transmitted through a UART interface, allowing for communication with other subsystems.

A 3.3 V switching regulator converts the external power input into a stable supply for the system, ensuring efficient and reliable operation. Supporting hardware such as decoupling capacitors, pull-up resistors, LEDs, pushbuttons, and test points improve reliability, enable debugging, and provide status indication. Ribbon cable connectors and expansion headers allow communication with other subsystems and support future expansion, ensuring the design meets system integration and communication requirements. The expansion headers were eventually used to support integration of the rotary encoder.


![image1](https://raw.githubusercontent.com/alazaritt/EGR314DataSheet/7f94780de71e25149b3370de543e7f6f2ffc9711/docs/05-Schematic/individual%20subsystem%20314.svg)
**Figure 1:** schematic of camera/rotary encoder subsystem.


## Resources

The schematic as a PDF download is available [*here*](https://github.com/alazaritt/EGR314DataSheet/releases/download/schematic/individual.subsystem.314.pdf), and the Zip folder of the project [*here*](https://github.com/alazaritt/EGR314DataSheet/releases/download/schematic/individual.subsystem.314.final.zip).
