---
#layout: page
#title: api
#permalink: /api/
title: API
has_toc: true
#has_children: true
nav_order: 4
layout: default
---

<style>
.tablelines table, .tablelines td, .tablelines th {
        border: 0px solid black;
        }
</style>

<style>
table th:first-of-type {
    width: 10%;
}
table th:nth-of-type(2) {
    width: 10%;
}
table th:nth-of-type(3) {
    width: 10%;
}
table th:nth-of-type(4) {
    width: 70%;
}
</style>

This is the API of the Techtile Robot Scissor Lift.

# Requests

| Name | Parameter | Data | Description |
|:-:|:-:|:-:|:-:|
| `<SL_CONNECTION_CHECK_REQ>`  | 0x01 | /   |   Check the connection     |
{: .tablelines}

| Name | Parameter | Data | Description |
|:-:|:-:|:-:|:-:|
| `<SL_CHANGE_SPEED_RPS_REQ>`  | 0x20 | 1 bytes | Set speed [Revolutions per second] |
| `<SL_CHANGE_SPEED_SPS_REQ>`  | 0x21 | 2 bytes | Set speed [Steps per second] |
| `<SL_CHANGE_DIR_CW_REQ>` | 0x22 | / | Change the direction to clockwise |
| `<SL_CHANGE_DIR_CCW_REQ>` |   0x23    |   /   |   Change the direction to counterclockwise |
| `<SL_MOVE_REV_REQ>` |   0x24    |   2 bytes   |   Move a number of revolutions |
| `<SL_MOVE_STP_REQ>` |   0x25    |   4 bytes   |   Move a number of steps |
{: .tablelines}

| Name | Parameter | Data | Description |
|:-:|:-:|:-:|:-:|
| `<SL_STOP_REQ>` |   0x30    |   4 bytes   |   Stop the machine now    |
{: .tablelines}

| Name | Parameter | Data | Description |
|:-:|:-:|:-:|:-:|
| `<SL_GETPOSITION_REQ>` |   0x40    |   4 bytes   |   Ask for current posistion |
{: .tablelines}


# Response messages

## Confirmations
A confirmations will be given on each request message.

| Name | Parameter | Description |
|:-:|:-:|:-:|
| `<SL_RX_MSG_CNF>` |   0xA0    |  Confirm message received |
{: .tablelines}

## Indications

| Name | Parameter | Description |
|:-:|:-:|:-:|
| `<SL_HOME_IND>` |   0x50    | Home posistion |
{: .tablelines}

