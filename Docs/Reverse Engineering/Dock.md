# iPod 30-Pin Dock Connector Research

## Overview

The Apple 30-pin dock connector was used across many iPod generations for:

* Charging
* USB data
* Audio output
* Accessory communication
* FireWire power/data on compatible models

This document contains known connector information. Device-specific usage still requires verification.

---

# Pinout

| Pin   | Signal           | Description                       |
| ----- | ---------------- | --------------------------------- |
| 1     | GND              | Ground                            |
| 2     | GND              | Ground                            |
| 3     | Right Audio      | Line out right                    |
| 4     | Left Audio       | Line out left                     |
| 5     | Right Input      | Audio input                       |
| 6     | Left Input       | Audio input                       |
| 8     | Composite Video  | Video output on supported models  |
| 11    | Serial GND       | Serial ground                     |
| 12    | TX               | Serial transmit                   |
| 13    | RX               | Serial receive                    |
| 18    | 3.3V             | Logic power                       |
| 21    | Accessory Detect | Accessory identification resistor |
| 23    | USB 5V           | USB power                         |
| 25    | USB D-           | USB data                          |
| 27    | USB D+           | USB data                          |
| 19/20 | FireWire Power   | 12V charging supply               |
| 22/24 | FireWire TPA     | FireWire data                     |
| 26/28 | FireWire TPB     | FireWire data                     |
| 29/30 | FireWire Ground  | Ground                            |

Unused or model-specific pins omitted.

---

# Reverse Engineering Notes

## Known

* The Nano uses Apple's 30-pin connector.
* USB charging/data is provided through the connector.
* Accessory detection uses resistor identification.

## Unknown

* Exact accessory detection resistances used by the 1st generation Nano.
* Active serial protocols.
* Which legacy FireWire pins are used internally.

---

# Linanify Design Considerations

Possible future support:

* USB charging through original dock connector.
* USB data connection.
* Accessory detection hardware.

Dock support does not need to be implemented for the first PCB revision but leaving electrical provisions may simplify future expansion.
