---
title: Cross define
has_toc: true
nav_order: 5
layout: default
---

```cpp
// ===========================================
// ===          ***  Requests ***          ===
// ===========================================
#define SL_CONNECTION_CHECK_REQ       0x01    //  Test the connection

  //  Start stop stepper motors
#define SL_STOP_REQ                   0x10    //  Stop stepper motors
#define SL_DS_REQ                     0x11    //  Go home downstairs
#define SL_US_REQ                     0x12    //  Go home upstairs
#define SL_MOVE_REV_REQ               0x13    //  Move a number of revolutions
#define SL_MOVE_STP_REQ               0x14    //  Move a number of steps

  //  Stepper motor settings
#define SL_CHANGE_SPEED_RPS_REQ       0x20    //  Change speed [Revolutions per second]
#define SL_CHANGE_SPEED_SPS_REQ       0x21    //  Change speed [Steps per second]
#define SL_DIR_CW_REQ                 0x22    //  Change direction clockwise (rise scissorlift)
#define SL_DIR_CCW_REQ                0x23    //  Change direction counterclockwise (descend scissorlift)

  //  Get commands
#define SL_ISHOME_DS_REQ              0x30    //  Get scissorlift in downstairs home position status     
#define SL_ISHOME_US_REQ              0x31    //  Get scissorlift in upstairs home position status
#define SL_ALTITUDE_REQ               0x32    //  Get altitude

// ===========================================
// ===       ***  Confirmations ***        ===
// ===========================================
#define SL_RX_MSG_CMF                 0xA0    //  Confirmation command received (checksum comfirmed)

// ===========================================
// ===        ***  Indications ***         ===
// ===========================================
#define SL_HOME_DS_IND                0x40    //  Indication home posistion downstairs
#define SL_HOME_US_IND                0x41    //  Indication home posistion upstairs

// ===========================================
// ===        ***  Responses ***           ===
// ===========================================
#define SL_ISHOME_DS_RSP              0x50    //  Return scissorlift in downstairs home position status        
#define SL_ISHOME_US_RSP              0x51    //  Return scissorlift in upstairs home position status
#define SL_ALTITUDE_RSP               0x53    //  Return altitude

```