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

### *Message Type 4 — Camera Status Report*

| Field         | Byte 1   | Byte 2       | Byte 3–4    | Byte 5–6     | Byte 7     |
| ------------- | -------- | ------------ | ----------- | ------------ | ---------- |
| Variable Name | reserved | camera_state | frame_width | frame_height | error_code |
| Variable Type | uint8_t  | uint8_t      | uint16_t    | uint16_t     | uint8_t    |
| Min Value     | 0        | 0            | 0           | 0            | 0          |
| Max Value     | 0        | 2            | 1920        | 1080         | 255        |
| Example       | 0        | 2            | 1280        | 1024         | 0          |

The camera subsystem does not transmit image frames. Instead, it periodically evaluates whether a camera is present using an I2C scan and assigns a simplified state:

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
