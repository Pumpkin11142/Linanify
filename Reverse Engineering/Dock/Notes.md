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
| 8 | Video Out | Composite video output (only when slideshow mode is active on iPod Photo) |
| 9 | S-Video Chroma | S-Video Chrominance output (iPod Color/Photo only) |
| 10 | S-Video Luma | S-Video Luminance output (iPod Color/Photo only) |
| 11 | GND | Serial GND |
| 12 | Tx | iPod sending line, serial TxD (UART/serial) |
| 13 | Rx | iPod receiving line, serial RxD (UART/serial) |
| 14 | n/a | not used |
| 15 | GND | Ground (-), internally connected with pin 16 on iPod motherboard |
| 16 | GND | USB GND (-), internally connected with pin 15 on iPod motherboard |
| 17 | n/a | not used |
| 18 | 3.3V | 3.3V Power (+) (logic rail) |
| 19 | +12V | FireWire Power 12VDC (+) |
| 20 | +12V | FireWire Power 12VDC (+) |
| 21 | Accessory Indicator / Serial enable | Different resistances to GND indicate accessory type; enables accessory-specific modes |
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
- Connector: Apple's 30-pin dock connector, used across many iPod/iPhone generations. Pin numbering is left-to-right when looking at the plug face — confirm orientation when probing.
- Power rails:
  - Pin 18: 3.3 V logic rail — used for accessory detection or powering low-power accessories in some setups.
  - Pin 23: 5 V (USB VBUS) — USB power from host/dock.
  - Pins 19 & 20: +12 V (FireWire charging on older docks) — legacy; many modern hosts supply only 5V.
- Accessory detection (Pin 21):
  - Apple used a resistor-to-ground ID method to differentiate accessory types (charging dock, car kit, remote, etc.).
  - Known resistor examples: values reported vary (e.g., 75 kΩ, 165 kΩ, 200 kΩ) — exact IDs are model-dependent. Marked as ??? where unclear.
- Serial (UART) on pins 12 (Tx) and 13 (Rx): typically 3.3V TTL levels, used by service/debug accessories on some models. Baud/framing: ??? (model-dependent).
- USB: Pins 25 (D-), 27 (D+) — standard USB differential pair. Follow USB specification for termination/pull resistors when emulating host or device.
- FireWire: TPA/TPB pairs (22/24/26/28) are legacy for high-speed data and charging on older iPods.
- Grounding: multiple ground pins (1,2,11,15,16,29,30) — verify continuity to mainboard ground before connecting.

## Common Tasks & Tips
- When probing, power off device first. Use DMM to find ground and power pins, then probe with scope only after verifying safe voltages.
- For accessory emulation, measure the actual resistance between Pin 21 and GND on a known-good accessory to reproduce detection.
- Avoid backfeeding power rails which can damage battery charging circuits; understand device power path before powering from docks.

## References
1. https://apple.fandom.com/wiki/30-pin_dock_connector#Pin_connectors  
2. ??? Apple Service Manual / Developer docs ???  
