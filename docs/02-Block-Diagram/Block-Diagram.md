---
title: Module's Block Diagram
tags:
- tag1
- tag2
---

## Overview
My subsystem operates using an ESP32 microcontroller, which serves as the central controller for a camera module and rotary encoder. The camera is capable of taking pictures and sending them as raw data packets. The rotary encoder tracks motor rotation and that input data through the system. The ESP32 manages all sensor behavior while also responding to control commands.

Power to the system is supplied via a 3.3V input, which can originate either from an external power supply or from another teammate’s system. This dual power option ensures that my system can operate fully independently or as part of a larger networked setup.

The system communicates actively with two other boards to maintain synchronization and operational awareness. It will send camera state updates to one board, allowing it to track the camera’s status and performance. The encoder data can also be transmitted over UART when requested. This board also has a manual override button and an LED to visually show status states.




## Block Diagram 

![Example of Indivial Block diagram ](https://raw.githubusercontent.com/alazaritt/EGR314DataSheet/ada3073d71bd5c960bf9477589850e1bda4c62a9/docs/02-Block-Diagram/individual2.0.drawio.svg)


The design of this subsystem was driven by the need to balance functionality with reliability and integration into the team’s overall system. Initially, the goal was to fully utilize the camera for image capture and data transmission, but challenges with hardware compatibility led to a focus on ensuring stable communication and consistent sensor behavior. As a result, the design prioritizes dependable camera operation at a basic level (capturing images and sending raw data) while also incorporating the rotary encoder as a reliable and easily verifiable input device. This approach ensured that multiple interfaces could be demonstrated as working within the system.

The block diagram reflects this decision making process by clearly organizing the subsystem into functional components. This includes the ESP32 as the central controller, the camera as a data generating sensor, the rotary encoder as an input sensor, and the UART interface for communication with other boards. This structure meets the product requirements by enabling the system to capture and transmit data, respond to external requests, and share status information across the network. 


A direct link to the source file of the above block diagram can be found [here](https://github.com/alazaritt/EGR314DataSheet/releases/download/blockdiagram/individual2.0.drawio)
