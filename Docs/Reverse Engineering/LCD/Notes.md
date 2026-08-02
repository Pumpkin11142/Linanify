# Data, Info, etc Related to the iPod's LCD
---
## Basic Information
| Parameter | Value | Notes |
|---|---|---|
| Controller | PortalPlayer SoC (display driven by SoC) ??? | Exact display driver IC (if separate) is ??? |
| Size (Diagonal) | 1.5" | In inches |
| Color Depth | 16-bit (65,536 colors) | Often reported as 16-bit for classic iPod displays |
| Type | Color LCD, LED backlit | Backlight may appear blue-white |
| Resolution | 176 × 132 px | Common for older iPod models |
| Dot Pitch | 0.168 mm | ??? verify measured value ??? |
| Interface | Parallel RGB / serial? ??? | Many small LCDs used an 8/9-bit parallel RGB interface or an SPI-like serial — unknown for this panel |
| Voltage(s) | Logic: 3.3V (typ) ; Backlight: ??? V / LED current ??? | Exact supply pins and voltages need probing and datasheet confirmation |
| Connector | Flexible cable / FPC with multiple pins ??? | Pinout model-specific; examine FPC traces for power/ground and data lines |

## Notes & Electrical / Timing
- Drive signals: small color LCDs typically require:
  - Pixel data lines (RGB bits)
  - Control signals: HSYNC, VSYNC (or DATA_EN), PCLK (pixel clock)
  - Power rails for logic and separate backlight supply
  - Some panels use a serial single-lane interface — unknown here, mark ??? where unsure.
- Backlight: LED backlight typically driven through a current-limited LED driver on the mainboard; direct connection to voltage without driver is not recommended.
- If the PortalPlayer SoC is the display source, timing and protocol are likely provided by embedded firmware; capturing signals with a logic analyzer while driving known image patterns can help map pins.

## Mechanical & Repair Notes
- Lcd usually glued into front bezel; removing requires careful prying and heat for adhesive.
- Ribbon cable is fragile — replace with a compatible FPC cable if damaged.
- Polarizer and glass scratches are common visible damage points.

## Reverse-Engineering / Probing Tips
- Identify GND and Vcc first with DMM before applying oscilloscope probes.
- If you have a working unit, capture the waveforms for pixel clock and data lines while showing known images (solid colors) — correlating data patterns to displayed colors helps find which lines are RGB and mapping order.
- For panels with unknown interface, look for labeled pads on FPC or trace thickness: wide bus-like traces often indicate parallel RGB lines.

## Unknowns / Items to Research
- Exact display part number: ???  
- Exact pinout and timing (PCLK, HS/VS, data bit order): ???  
- Backlight drive voltage/current and connector pin: ???  

## References
- Panel datasheets (search by part number from label) — ???  
- iPod teardowns and community notes (iFixit, forums)  
