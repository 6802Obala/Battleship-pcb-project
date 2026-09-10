# 🚢 Battleship PCB — Embedded System & Board Bring-Up

Welcome to the repository for the **Battleship PCB** project, developed during the Advanced Computer Engineering 1 course at **HTW Berlin** (Summer Semester 2026).

This project covers the full hardware product development lifecycle: from schematic capture and multi-layer PCB layout in Altium Designer to hands-on SMT reflow assembly, manual soldering rework, and complete system commissioning.

---

## 👥 Authors & Team
* **Marc Kengnang** 
* **Stanislav (Stas) Osipov** 

---

## 📄 Project Documentation & Protocol
You can read or download the complete **Inbetriebnehmeprotokoll (Hardware Bring-Up & Test Report)** directly here:
👉 **[View the Inbetriebnehmeprotokoll PDF](./Inbetriebnehmeprotokoll_battleship.pdf)**

---

## 🛠️ Technical Specifications & System Overview

* **Microcontroller:** Raspberry Pi Pico W (handling game logic, inputs, and display rendering).
* **Display Matrix:** $20 \times 10$ Grid (200 individually addressable WS2812B-3535 RGB LEDs).
* **Power Supply:** On-board 12V-to-5V Step-Down Buck Converter (TPS54531DDAR) with power MOSFETs & Schottky diodes.
* **Peripherals:** 
  * KY-023 Analog Joystick (cursor movement)
  * Mechanical Push-buttons (firing / action inputs)
  * Buzzer (audio feedback)
  * SBC-OLED01 Display Interface

---

## 🔧 Hardware Rework & Lessons Learned (*Lötübungen*)

During the assembly and bring-up phase (*Inbetriebnahme*), several real-world engineering challenges were solved with hands-on hardware rework:

1. **Inductor Footprint Modification:** Mounted a 5A power inductor via raised solder feet (free-wiring/air-wiring) to adapt to a smaller PCB footprint.
2. **PCB Trace Repair:** Re-bridged a damaged 5V trace with copper jumper wire following component rework.
3. **Component Re-alignment:** Re-soldered SMD push-buttons and directly wired joystick analog axes ($VRx/VRy$) to the Pico's ADC pins to fix routing issues.
4. **Power Rail Verification:** Performed systematically with a digital multimeter and benchtop DC power supply before flashing game software.

---

## 🧰 Tools & Software Used
* **EDA / CAD:** Altium Designer (Schematic Capture, Multi-layer Layout, Stencil Definition)
* **Lab Equipment:** Reflow Oven, Solder Paste Stencil, Vacuum Pick-and-Place tool, Digital Multimeter, Bench Power Supply, Soldering/Rework Station.
* **Firmware / Testing:** MicroPython / Python scripts for hardware bring-up and game state testing.
