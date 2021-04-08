---
title: Frame
has_toc: true
#has_children: true
nav_order: 3
layout: default
---


# Communication Frame

The configurations and the operation of the scissor lift can be managed by predefined commands that are sent as telegrams over the UART interface.

| Start Delimiter | Command | Length | Payload | Checksum |
|:-------:|:--------:|:---------:|:---------:|:----------:|
| 1 byte | 1 byte | 1 byte  | length bytes | 1 byte |
{: .tablelines}

* **Start Delimiter:**     Each frame start with 0x02
* **Command:**          One of the predefined commands ([API](api.markdown)).
* **Length:**           Specifies the length of the data that follows.
* **Payload:**          Variable number (defined by the length field) of data or parameters.
* **Checksum:**         Byte wise XOR combination of all preceding Bytes including the start signal. 
                    E.g. 0x02 ˆ Command ˆ Length ˆ Payload = CS