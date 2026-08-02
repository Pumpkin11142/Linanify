# iPod Nano 1st Generation Click Wheel

## Overview

The iPod Nano click wheel combines:

* Capacitive touch sensing for rotational input.
* Mechanical switches for button presses.

The click wheel is controlled by a dedicated Cypress PSoC microcontroller.

---

# Hardware

| Component  | Value                   | Notes                                    |
| ---------- | ----------------------- | ---------------------------------------- |
| Controller | Cypress CY8C21001A PSoC | Handles capacitive sensing               |
| Input Type | Capacitive touch        | Used for wheel rotation                  |
| Buttons    | Mechanical switches     | Menu, Select, Play/Pause, Previous, Next |
| Connection | Flexible PCB cable      | Connects wheel assembly to motherboard   |

---

# Functional Mapping

| Area          | Function          |
| ------------- | ----------------- |
| Outer ring    | Scroll input      |
| Center button | Select            |
| Top button    | Menu              |
| Bottom button | Play/Pause        |
| Left button   | Previous/Rewind   |
| Right button  | Next/Fast Forward |

---

# Reverse Engineering Status

## Confirmed

* Click wheel uses capacitive sensing.
* Cypress CY8C21001A PSoC is present.
* Mechanical buttons are separate inputs.

## Unknown

* Communication protocol between CY8C21001A and PortalPlayer PP5021.
* Exact click wheel FPC pinout.
* Whether communication uses I2C, SPI, GPIO, or another proprietary interface.

---

# Reverse Engineering Plan

1. Map FPC connector pins.
2. Identify ground and power pins using a multimeter.
3. Capture communication between the click wheel controller and main SoC.
4. Determine data format for:

   * rotation direction
   * rotation speed
   * button presses
5. Implement replacement controller interface if needed.

---

# Linanify Design Considerations

The preferred approach is preserving the original click wheel hardware.

Possible solutions:

1. Interface directly with the CY8C21001A output.
2. Replace the controller with a modern capacitive touch controller.
3. Create firmware that translates the original signals into Linux input events.

The first option preserves the authentic iPod experience.
