---
title: Serial Connection
has_toc: true
#has_children: true
nav_order: 2
layout: default
---

<style>
.tablelines table, .tablelines td, .tablelines th {
        border: 0px solid black;
        }
</style>

# Serial Connection

A serial connection allows the communication between the scissor lift MCU and raspberry pi or PC. The two corresponding COM ports have to be selected and opened with a default configuration of 115200 Baud, 8 data Bits, 1 stop Bit and parity set to none (8n1).

| Parameter    | Format |
| ------------ | ------ |
| Baudrate     | 115200 |
| data bits    | 8      |
| parity       | none   |
| stop bits    | 1      |
| flow control | off    |
|-----------|--------|-------------|
{: .tablelines}


# Command interface

The configurations and the operation of the scissor lift can be managed by predefined commands that are sent as telegrams over the UART interface.

| Start signal | Command | Length | Payload | Checksum |
|:-------:|:--------:|:---------:|:---------:|:----------:|
| 1 byte | 1 byte | 1 byte  | length bytes | 1 byte |
{: .tablelines}

* **Start signal:**     Each frame start with 0x02
* **Command:**          One of the predefined commands ([API](api.markdown)).
* **Length:**           Specifies the length of the data that follows.
* **Payload:**          Variable number (defined by the length field) of data or parameters.
* **Checksum:**         Byte wise XOR combination of all preceding Bytes including the start signal. 
                    E.g. 0x02 ˆ Command ˆ Length ˆ Payload = CS