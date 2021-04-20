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


## Send a command

Payload data is sometimes unnecessary. Only a command is send to the scissorlift. You can just send the command and use a length of zero.

```cpp
0x02 0x10 0x00 0x12 //  Example command frame without payload
```

## Send a command with payload

The payload bytes of length n can be sent very easily. Before the frame can be sent, the exact length of the bytes to be sent must be known. If the length and the number of bytes of the payload do not match, the incoming frame is ignored.

```cpp
0x02 0x10 0x03 0x01 0x02 0x03 0x11 //  Example command 0x10 with payload 0x01 0x02 0x03
```

# Receiving Frame

