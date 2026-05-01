---
title: API
tags:
- tag1
- tag2
---


## Overview

My subsystem is a combined camera status and rotary encoder reporting module. Its primary role is to interface with a camera over I2C to determine whether it is connected and functioning, and to communicate this status over a daisy-chained UART network. In addition to the camera subsystem, it also reads a rotary encoder using GPIO inputs to track rotation direction and button presses. Both the camera status and encoder data are reported to other subsystems when requested through the shared communication protocol.

The subsystem focuses on reporting camera state information such as whether the camera is detected, whether it is considered “capturing,” and any associated error conditions. An onboard LED is used as a simple debug indicator for transmission activity and is not part of the communication protocol itself.

All communication follows the shared UART packet protocol, which defines message framing, addressing, and routing rules for all subsystems in the network.

## Messages Received/Processed

* Messages received that are addressed to this subsystem are parsed and processed through a validation and routing system.
* If a message is a valid request from the HMI, the subsystem responds with either camera status data or encoder data depending on the request type.
* Messages not intended for this subsystem are automatically forwarded along the UART daisy chain without modification.
* Messages that originate from this subsystem and loop back to it are discarded to prevent redundant processing.
* Any improperly formatted or invalid packets are rejected during validation and not further processed.
* An acknowledgement is only generated for valid, correctly formatted messages.

## Messages Sent

This subsystem sends two main message types:
Message Type 4 – Camera Status Report and Message Type 5 – Encoder Status Report.
Both are structured according to the shared UART protocol and are transmitted only in response to valid requests from the HMI.
All message fields use fixed width integer types (uint8_t, uint16_t) that are consistent with the UART protocol definition.

### *Team IDs*

| Name | Subsystem Role | Board ID |
|------|----------------|---------------|
| Christo | HMI Interface | 0x43 |
| Liam | Motor Control | 0x4C |
| Isaiah | Environmental Sensing | 0x49 |
| Arianna | Camera | 0x41 |
| Myles | Distance Sensing | 0x4D |
| Ragul | Gyroscope | 0x52 |
| Damian | MQTT | 0x44 |
| System | Broadcast | 0x58 |

### *Message Type 4 — Camera Status Report*

| Field         | Byte 1   | Byte 2       | Byte 3–4    | Byte 5–6     | Byte 7     |
| ------------- | -------- | ------------ | ----------- | ------------ | ---------- |
| Variable Name | reserved | camera_state | frame_width | frame_height | error_code |
| Variable Type | uint8_t  | uint8_t      | uint16_t    | uint16_t     | uint8_t    |
| Min Value     | 0        | 0            | 0           | 0            | 0          |
| Max Value     | 0        | 2            | 1920        | 1080         | 255        |
| Example       | 0        | 2            | 1280        | 1024         | 0          |

The camera subsystem does not transmit image frames. Instead, it periodically evaluates whether a camera is present using an I2C scan for the expected device address and assigns a simplified state:

* Camera present = state set to capturing
* Camera missing for multiple checks = state set to off with an error code

This status data is only transmitted when requested by the HMI.


### *Message Type 5 — Encoder Status Report*

| Field         | Byte 1–2      | Byte 3–4       | Byte 5–6    |
| ------------- | ------------- | -------------- | ----------- |
| Variable Name | forward_count | backward_count | reset_count |
| Variable Type | uint16_t      | uint16_t       | uint16_t    |
| Min Value     | 0             | 0              | 0           |
| Max Value     | 65535         | 65535          | 65535       |
| Example       | 12            | 8              | 1           |

The rotary encoder subsystem tracks:

* Forward rotation steps
* Backward rotation steps
* Button presses used to reset counters

These values are updated continuously in software and transmitted when requested by the HMI. This allows external systems to monitor user input in real time.


## Receiving Message Structure

* Incoming messages are validated for correct format, length, and addressing before processing
* Requests from the HMI trigger either a camera status response or encoder status response
* Messages not addressed to this subsystem are forwarded unchanged
* Loopback messages (originating from this subsystem) are discarded
* Only valid request messages generate a response


## Outgoing Message Structure

* The subsystem primarily responds to requests rather than continuously streaming data
* Encoder and camera status messages are only transmitted when requested
* Forwarding of unrelated messages is prioritized over generating new outgoing data
* All outgoing messages follow the shared UART packet structure with proper framing and addressing



The following 2 tables define the complete packet structure used when the HMI requests camera status information. It includes both the request format sent to the camera subsystem and the corresponding response format returned by it. These packets follow the shared UART protocol and demonstrate how the request travels through the system and triggers a structured response.

### *Packet Exchange — Camera Status Request & Response*

| Field         | Byte 1–2   | Byte 3    | Byte 4      | Byte 5   | Byte 6–61   | Byte 62–63 |
| ------------- | ---------- | --------- | ----------- | -------- | ----------- | ---------- |
| Variable Name | prefix     | sender_id | receiver_id | msg_type | payload     | suffix     |
| Variable Type | uint8_t[2] | uint8_t   | uint8_t     | uint8_t  | uint8_t[57] | uint8_t[2] |
| Value         | 0xA5 0x5A  | 0x43      | 0x41        | 0x14     | 0x04 ...    | 0x59 0x42  |

### *Camera Node to HMI (Camera Status Response)*

| Field         | Byte 1–2   | Byte 3    | Byte 4      | Byte 5   | Byte 6–61                  | Byte 62–63 |
| ------------- | ---------- | --------- | ----------- | -------- | -------------------------- | ---------- |
| Variable Name | prefix     | sender_id | receiver_id | msg_type | payload                    | suffix     |
| Variable Type | uint8_t[2] | uint8_t   | uint8_t     | uint8_t  | uint8_t[57]                | uint8_t[2] |
| Value         | 0xA5 0x5A  | 0x41      | 0x43        | 0x04     | 0x00 02 00 05 00 04 00 ... | 0x59 0x42  |

### *Payload Breakdown — Camera Status Response*

Once a valid camera status request is received and processed, my subsystem generates a response packet addressed back to the HMI. This response follows the same communication structure as the request but contains system specific status information derived from an I2C device scan. The payload encodes the current camera state along with configuration and error data.

| Field         | Byte 1   | Byte 2       | Byte 3–4    | Byte 5–6     | Byte 7     |
| ------------- | -------- | ------------ | ----------- | ------------ | ---------- |
| Variable Name | reserved | camera_state | frame_width | frame_height | error_code |
| Variable Type | uint8_t  | uint8_t      | uint16_t    | uint16_t     | uint8_t    |
| Value         | 0        | 2            | 1280        | 1024         | 0          |


### *Encoder Status Response (HMI Request to Camera)*

This defines the packet structure used for retrieving rotary encoder data from my subsystem. Similar to the camera status exchange, the HMI sends a request message that triggers a response containing encoder counters. The encoder values reflect real time input tracking and are transmitted only when explicitly requested through the shared UART protocol.

| Field         | Byte 1–2   | Byte 3    | Byte 4      | Byte 5   | Byte 6–7   | Byte 8–9   | Byte 10–11 | Byte 12–61  | Byte 62–63 |
| ------------- | ---------- | --------- | ----------- | -------- | ---------- | ---------- | ---------- | ----------- | ---------- |
| Variable Name | prefix     | sender_id | receiver_id | msg_type | forward_lo | forward_hi | back_lo    | payload     | suffix     |
| Variable Type | uint8_t[2] | uint8_t   | uint8_t     | uint8_t  | uint8_t    | uint8_t    | uint8_t    | uint8_t[57] | uint8_t[2] |
| Value         | 0xA5 0x5A  | 0x41      | 0x43        | 0x05     | varies     | varies     | varies     | 0x00 ...    | 0x59 0x42  |
