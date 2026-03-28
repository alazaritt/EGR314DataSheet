---
title: API
tags:
- tag1
- tag2
---

## Overview
My subsystem is the camera subsystem. Its primary role is to capture image frames using an onboard camera and communicate both status information and image data over the daisy-chained UART network. The subsystem periodically reports the camera’s operating state (idle or capturing) and transmits captured frames in packetized chunks to other subsystems. An onboard LED is used for debugging the system and is not part of the communication interface.

The team communication protocol defines standard message types for subsystem interaction over UART. For my subsystem, the primary communication involves reporting camera status and sending image frame data in packets. All messages sent follow the shared UART protocol with framing and addressing constraints.

## Messages Received/Processed
* Messages received that are intended for this subsystem will be acknowledged by flashing an onboard LED (not connected to the UART message system)
* Any messages not addressed to this subsystem are forwarded to other subsystems along the UART daisy chain system.
* Any messages sent from this subsystem that have circled back to it will be discarded.
* Messages that are not properly formatted and are larger than the payload size will be ignored
* 


## Messages Sent
This subsystem sends two different message types, Message Type 3 – Camera Frame Data Packets, and Message Type 4 — Camera Status Report. All messages are formatted according to the shared team protocol and include a unique message type identifier, relevant data fields, and optional error codes. The tables below outline how the messages are constructed and sent.


### *Message Type 3 — Camera Frame Data Packets*

| Field          | Byte 1–2 | Byte 3–4 | Byte 5–6 | Byte 7–8 | Byte 9–58 |
|----------------|----------|----------|----------|----------|-----------|
| Variable Name  | message_type | frame_id | packet_index | total_packets | image_data_chunk |
| Variable Type  | uint16_t | uint16_t | uint16_t | uint16_t | uint8_t[50] |
| Min Value      | 3        | 0        | 0        | 1        | 0         |
| Max Value      | 3        | 65535    | 65535    | 65535    | 255       |
| Example        | 3        | 25       | 1        | 10       | 45        |

Each captured frame is divided into multiple packets, with each packet containing up to 50 bytes of image data. The packet_index field indicates the order of the packet within the frame, and total_packets tells the receiver how many packets to expect for the full frame. This allows the receiving subsystem to reconstruct the complete image frame from multiple chunks. Packet size and sequence numbering ensure consistent and reliable transmission over the UART daisy chain.

*Value Breakdown*

* message_type: Indicates this is an image data packet
* frame_id: Unique ID for each captured frame
* packet_index: Sequence number of this chunk
* total_packets: Total number of packets for the full frame
* image_data_chunk: Raw image data

### *Message Type 4 — Camera Status Report*

| Field          | Byte 1–2 | Byte 3 | Byte 4–5 | Byte 6–7 | Byte 8 |
|----------------|----------|--------|----------|----------|--------|
| Variable Name  | message_type | camera_state | frame_width | frame_height | error_code |
| Variable Type  | uint16_t | uint8_t | uint16_t | uint16_t | uint8_t |
| Min Value      | 4        | 0      | 0        | 0        | 0      |
| Max Value      | 4        | 2      | 1920     | 1080     | 2      |
| Example        | 4        | 2      | 640      | 480      | 0      |

The camera subsystem periodically sends a status report and splits each captured frame into the following values for transmission:

*Value Breakdown*

* camera_state: 0 = Off, 1 = Idle, 2 = Capturing
* frame_width and frame_height: Resolution of captured frames
* error_code: 0 = No error, 1 = Camera not detected, 2 = Unknown error



### Receiving Message Structure

* Check message validity
* Discard looped messages that originated from this subsystem
* Process messages addressed to this subsystem
* Forward all other messages unchanged
* Provide a unique acknowledgement when a correctly formatted message received

### Outgoing Message Structure
* All non-local messages are retransmitted
* Prioritize forwaring received messages over sending new messages
* The subsystem periodically transmits Message Types 3 and 4
