---
title: Module's Requirements
---

## Module Requirements
The table below outlines the initla critical requirements that were outlined for the Imaging Control subsystem. This subsystem is responsible for controlling the rover’s camera, capturing images and video, packetizing the data for transmission, and providing status feedback to the operator. The table outlines the minimum acceptable performance, the target goals, and optional stretch requirements for each feature within the subsystem. Specifying these measures allows to systematically verify that the subsystem meets both functional and integration expectations

Each requirement in the table is tied to a measurable outcome so it can be determined whether the subsystem performs at a threshold level, meets the target performance, or exceeds expectations with enhanced features. This structured approach ensures that design decisions are justified, potential risks are identified early, and the subsystem integrates seamlessly with my team’s overall rover system.


| **Requirement Description** | **Measure of<br> Threshold** | **Target<br>Measure** |**Stretch<br>Requirement<br>(Y-N)**|
|-----------------------------| ----------------- | ----------------- | :-----: |
| Surface mounted, 3.3V switching power regulatore | 3.2 Volts | 3.3 Volts | No |
| Surface mounted microcontroller | ESP32 | programmed in MicroPython | No |
| Wireless Communication | Able to send or receive basic Wi-Fi data | Send and receive Wi-Fi Data to MQTT | Yes |
| Camera Operation | Able to capture images reliably | Image is recieved | No |
| Video Capture | Able to capture low-resolution video | Real-time video streaming | No |
| Data Packets | Packetizes image data for transmission | Packetizes with minimal loss | Yes |
| Status Reporting | Reports device state | Reports imaging and operation status back to user | No |
| UART Communication | Can send/recieve messages over UART | Complete data transmission between other subsystems | Yes |
| Human-Machine Interface | Can visually display data to users | Able to clearly display imaging/video data | No |
| HMI Camera Control | Able to pan camera left/right based on user input | Manual pan/tilt with screen display feedback | Yes |
