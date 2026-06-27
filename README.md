
# CAN-Based Automotive Dashboard System using PIC18F4580

## Overview

The CAN-Based Automotive Dashboard System is an embedded systems project that simulates communication between multiple Electronic Control Units (ECUs) using the Controller Area Network (CAN) protocol.

The project consists of three PIC18F4580 microcontrollers connected through MCP2551 CAN transceivers. Two ECUs generate vehicle parameters such as speed, RPM, gear position, and turn indicator status, while the third ECU acts as the dashboard by receiving CAN messages and displaying the information on a Character LCD in real time.

This project demonstrates real-time CAN communication, interrupt handling, and peripheral interfacing using Embedded C.

---

## Features

- Three-ECU CAN network
- Real-time communication using CAN protocol
- Speed monitoring
- RPM monitoring
- Gear position display
- Left and Right indicator status
- Character LCD dashboard
- Interrupt-driven CAN message reception
- Modular Embedded C implementation

---

## Hardware Used

- PIC18F4580 Microcontroller ×3
- MCP2551 CAN Transceiver ×3
- Character LCD (16×2)
- Matrix Keypad
- LEDs
- Crystal Oscillator
- Power Supply

---

## Software Used

- MPLAB X IDE
- XC8 Compiler
- Embedded C

---

## System Architecture

```
                   CAN BUS
----------------------------------------------------------

        ECU-1                    ECU-2
+------------------+      +------------------+
| Speed Control    |      | RPM Control      |
| Gear Selection   |      | LED Indicators   |
| PIC18F4580       |      | PIC18F4580       |
+--------+---------+      +---------+--------+
         |                          |
         |                          |
         +----------- CAN ----------+
                     |
                     |
              +------+------+
              |   ECU-3     |
              | Dashboard   |
              | PIC18F4580  |
              | LCD Display |
              +-------------+
```

---

## ECU Description

### ECU-1
- Generates vehicle speed
- Controls gear selection
- Transmits Speed and Gear data over CAN

### ECU-2
- Generates engine RPM
- Controls Left and Right indicators
- Transmits RPM and Indicator status over CAN

### ECU-3 (Dashboard ECU)
- Receives CAN messages from ECU-1 and ECU-2
- Decodes received CAN frames
- Displays:
  - Vehicle Speed
  - Engine RPM
  - Gear Position
  - Indicator Status
- Updates the dashboard display in real time

---

## Working

1. ECU-1 generates vehicle speed and gear information.
2. ECU-2 generates engine RPM and indicator status.
3. Both ECUs transmit their data over the CAN bus.
4. ECU-3 receives CAN messages using interrupts.
5. The received information is decoded and displayed on the Character LCD.
6. The dashboard continuously updates with the latest vehicle information.

---

## Technologies Used

- Embedded C
- PIC18F4580 Microcontroller
- CAN Protocol
- MCP2551 CAN Transceiver
- MPLAB X IDE
- XC8 Compiler

---

## Project Structure

```
CAN-Based-Automotive-Dashboard/
│
├── ECU1.X
│   ├── Source Files
│   ├── Header Files
│   └── MPLAB Project Files
│
├── ECU2.X
│   ├── Source Files
│   ├── Header Files
│   └── MPLAB Project Files
│
├── ECU3.X
│   ├── Source Files
│   ├── Header Files
│   └── MPLAB Project Files
│
├── Images
│   ├── Block_Diagram.png
│   ├── Hardware_Setup.jpg
│   └── Dashboard_Output.jpg
│
└── README.md
```

---

## Challenges Faced

- Configuring CAN baud rate for reliable communication.
- Synchronizing communication between three ECUs.
- Debugging CAN transmission and reception.
- Integrating multiple peripherals with CAN communication.
- Managing interrupt-driven CAN message handling.

---

## Learning Outcomes

- CAN protocol implementation
- Multi-node ECU communication
- PIC18F4580 CAN peripheral configuration
- Interrupt handling
- Embedded C programming
- Automotive embedded systems
- Driver-based software development

---

## Future Improvements

- Fuel level monitoring
- Engine temperature display
- Odometer
- Warning indicators
- CAN diagnostics
- TFT graphical dashboard
- Data logging over UART
