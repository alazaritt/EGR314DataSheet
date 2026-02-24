---
title: Module's Block Diagram
tags:
- tag1
- tag2
---

## Overview
The imaging system for my team’s rover operates using an ESP32 microcontroller, which serves as the central controller for a camera module. The camera is capable of live-streaming video over Wi-Fi, enabling real-time monitoring and data capture. The ESP32 manages all camera operations, including initialization, streaming, and responding to control commands.

Power to the system is supplied via a 3.3V input, which can originate either from an onboard power source or from a teammate’s system. This dual power option ensures the system can operate fully independently or as part of a larger networked setup.

The system communicates actively with two other boards to maintain synchronization and operational awareness. It will send regular state updates to one board, allowing it to track the camera’s status and performance. It can also  receive commands from a second board to turn the camera on or off, enabling control across a multi-device interface.



## Block Diagram 

![Example of Indivial Block diagram ](https://raw.githubusercontent.com/alazaritt/EGR314DataSheet/05a2e06ff7b738945f76b8e05a344b244da6ed41/docs/02-Block-Diagram/individual2.0.drawio.svg)


A direct link to the source file of the above block diagram can be found [here](https://github.com/alazaritt/EGR314DataSheet/releases/download/blockdiagram/individual2.0.drawio)
