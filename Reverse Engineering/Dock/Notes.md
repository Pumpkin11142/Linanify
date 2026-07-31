# Data, Info, etc Related to the iPod's Dock Connector
---
## Pin Connectors <sup>[1]</sup>
| Pin | Signal | Description |
|---|---|---|
| 1 | GND | Ground (-), internally connected with Pin 2 on iPod motherboard |
| 2 | GND | Audio and Video ground (-), internally connected with Pin 2 on iPod motherboard |
| 3 | Right | Line Out - R (+) (Audio output, right channel) |
| 4 | Left | Line Out - L (+) (Audio output, left channel) |
| 5 | Right In | Line In - R (+) |
| 6 | Left In | Line In - L (+) |
| 7 | ? | ??? Function unknown / varies by accessory ??? |
| 8 | Video Out | Composite video output (only when the slideshow mode is active on iPod Photo) |
| 9 | S-Video Chroma | S-Video Chrominance output (iPod Color/Photo only) |
| 10 | S-Video Luma | S-Video Luminance output (iPod Color/Photo only) |
| 11 | GND | Serial GND |
| 12 | Tx | iPod sending line, serial TxD (UART/serial) |
| 13 | Rx | iPod receiving line, serial RxD (UART/serial) |
| 14 | n/a | not used |
| 15 | GND | Ground (-), internally connected with pin 16 on iPod motherboard |
| 16 | GND | USB GND (-), internally connected with pin 15 on iPod motherboard |
| 17 | n/a | not used |
| 18 | 3.3V | 3.3V Power (+) (logic power rail) |
| 19 | +12V | FireWire Power 12VDC (+) |
| 20 | +12V | FireWire Power 12VDC (+) |
| 21 | Accessory Indicator / Serial enable | Different resistances to ground indicate accessory type / enable serial on older models |
| 22 | TPA (-) | FireWire TPA (-) |
| 23 | 5 VDC (+) | USB Power 5 VDC (+) |
| 24 | TPA (+) | FireWire TPA (+) |
| 25 | Data (-) | USB Data (-) (D-) |
| 26 | TPB (-) | FireWire Data TPB (-) |
| 27 | Data (+) | USB Data (+) (D+) |
| 28 | TPB (+) | FireWire Data TPB (+) |
| 29 | GND | FireWire Ground (-) |
| 30 | GND | FireWire Ground (-) |

---

## Notes & Electrical
- Connector: Apple's 30-pin dock connector, used across many iPod/iPhone generations. Pin numbering is from left-to-right looking at the male plug (verify orientation when measuring).
- Power rails:
  - Pin 18: 3.3 V (logic) — used to power internal logic or to detect docking state in some accessories.
  - Pin 23: 5 V (USB VBUS) — USB power from host/dock.
  - Pins 19 & 20: +12 V (FireWire charging on older docks) — not present/used on modern USB-only docks.
- Accessory detection (Pin 21): Apple used resistor-based ID on this pin so that different dock/accessory types can be identified. Common reported resistor values include examples like 75 kΩ, 165 kΩ, 200 kΩ, etc. Exact mapping to accessory types varies by model and is ??? (verify exact values per model) ???.
- Serial (UART) on pins 12 (Tx) and 13 (Rx): often 3.3V TTL levels, used by service/debug accessories and some accessories that use a serial protocol. Baud rate / framing is ??? (model-dependent) ???.
- USB signals: Pins 25 (D-), 27 (D+) — standard USB differential pair. Use standard USB termination and pull-up/pull-down resistors when emulating a host/device.
- FireWire signals: TPA/TPB pairs on 22/24/26/28 — legacy, primarily for older iPod generations; usually not needed for modern charging/hacking.

## Common Tasks & Tips
- When probing the connector, always power down the iPod and use a multimeter first to identify grounds and power rails before applying signals.
- If reverse-engineering accessories, measure resistor value on Pin 21 to identify accessory ID behavior for your specific iPod model.
- Beware of back-powering: connecting 5V to the dock while other power sources are present can damage the device unless power paths are understood.

## References
1. https://apple.fandom.com/wiki/30-pin_dock_connector#Pin_connectors  
2. ??? Additional authoritative references (Apple service manuals, hobbyist pinout pages) ???
