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
| Baudrate     | 1000000 |
| data bits    | 8      |
| parity       | none   |
| stop bits    | 1      |
| flow control | off    |
|-----------|--------|-------------|
{: .tablelines}