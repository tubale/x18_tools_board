# ROV Tools Board

A custom **4-layer STM32-based PCB** designed for Purdue IEEE Underwater Robotics to control a six-servo robotic arm. This project involved the complete hardware development cycle, including system architecture, schematic design, PCB layout, power distribution, board bring-up, debugging, and integration into the ROV.

---

## Overview

The Tools Board serves as the interface between the Raspberry Pi and the ROV's robotic arm. It provides reliable power delivery, real-time servo control, and SPI communication while operating in a high-current, electrically noisy environment.

This project was designed from the ground up using KiCad and assembled, tested, and validated on the team's underwater robot.

---

## Features

- Custom **4-layer PCB** designed in **KiCad**
- **STM32 microcontroller** for real-time control
- Controls **6 independent servo motors**
- Supports up to **4A peak current**
- High-efficiency **12V → 6V buck converter**
- **5V → 3.3V LDO** for the STM32 and logic circuitry
- **SPI communication** with Raspberry Pi
- Optimized PCB layout with isolated power planes for improved signal integrity
- Hand assembled and fully validated through hardware bring-up

---

## Hardware Architecture

```text
                 Raspberry Pi
                      │
                   SPI Interface
                      │
              ┌───────────────┐
              │   STM32 MCU   │
              └───────────────┘
          PWM │ │ │ │ │ │
              ▼ ▼ ▼ ▼ ▼ ▼
        ┌────────────────────┐
        │   6 Servo Outputs  │
        └────────────────────┘

12V Input
    │
    ▼
┌──────────────┐
│ Buck 12V→6V  │────────► Servos
└──────────────┘
    │
    ▼
┌──────────────┐
│ LDO 5V→3.3V  │────────► STM32 + Logic
└──────────────┘
```

---

## Design Process

### System Architecture

- Defined power and communication requirements
- Selected STM32 microcontroller
- Designed SPI interface with Raspberry Pi
- Planned high-current power distribution for servo operation

### Schematic Design

Designed the complete electrical schematic including:

- STM32 microcontroller
- Servo outputs
- SPI interface
- Programming/debug connector
- Buck converter
- LDO regulator
- Decoupling and filtering circuitry
- Status LEDs
- Connectors

### PCB Layout

Designed a **4-layer PCB** with:

- Dedicated ground plane
- Dedicated power plane
- High-current routing for servo power
- Short SPI signal paths
- Proper decoupling placement
- Separation between noisy power circuitry and sensitive digital signals

### Assembly

- Soldered surface-mount and through-hole components
- Inspected and verified board assembly
- Performed continuity testing before power-up

### Bring-Up & Validation

Verified each subsystem independently using:

- Digital Multimeter
- Oscilloscope
- Logic Analyzer

Testing included:

- Power rail verification
- SPI communication
- PWM generation
- Servo functionality
- Current measurements
- Signal integrity

---

### Technologies

**Hardware:** KiCad • STM32 • SPI • PWM • 4-Layer PCB Design • Buck Converter Design • LDO Voltage Regulation

**Testing:** Oscilloscope • Logic Analyzer • Digital Multimeter

---

## Gallery

### Schematic

<p align="center">
  <img src="Pictures/Schematic.png)" width="700">
</p>


### Layout

<p align="center">
  <img src="Pictures/Layout.png)" width="700">
</p>

### Assembled Board

<p align="center">
  <img src="Pictures/Tools_board.png)" width="700">
</p>

---

## Author

**Tanay Ubale**

Electrical & Computer Engineering Student at Purdue University

Interested in Digital Design, FPGA Development, ASIC Design, Embedded Systems, PCB Design, and Computer Architecture.
