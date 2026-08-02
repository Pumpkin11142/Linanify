# iPod Nano 1st Generation LCD

## Overview

The 1st generation iPod Nano uses a small color LCD driven by the PortalPlayer PP5021 system-on-chip.

The display panel itself is separate from the SoC and communicates through a flexible cable connection.

---

# Known Specifications

| Parameter    | Value              | Notes                             |
| ------------ | ------------------ | --------------------------------- |
| Size         | 1.5 inch           | Diagonal measurement              |
| Resolution   | 176 × 132 pixels   | Confirmed for 1st generation Nano |
| Color Depth  | 16-bit             | 65,536 colors                     |
| Display Type | Color LCD          | LED backlight                     |
| Connector    | Flexible PCB cable | Exact pinout unknown              |

---

# Display Architecture

Known:

* PortalPlayer PP5021 contains display interface hardware.
* LCD panel receives data from the SoC.
* Backlight requires separate power handling.

---

# Unknown

* Exact LCD panel manufacturer/model.
* FPC pinout.
* Data bus width.
* Pixel clock frequency.
* RGB bit ordering.
* Backlight voltage/current requirements.

---

# Reverse Engineering Plan

1. Photograph and document LCD flex cable.
2. Determine connector pin count and spacing.
3. Identify ground pins using continuity testing.
4. Identify power rails.
5. Capture display signals with a logic analyzer.
6. Determine:

   * communication protocol
   * pixel format
   * timing requirements

---

# Linanify Design Considerations

Keeping the original LCD is preferred because:

* It preserves the original appearance.
* It avoids modifying the enclosure.
* It maintains the original industrial design.

A replacement motherboard must reproduce the electrical interface expected by the LCD.

Potential approaches:

1. Use a Linux-capable SoC with compatible display output.
2. Add an intermediate display controller.
3. Replace the LCD interface entirely while retaining the physical panel.

Current preferred option:

Reverse engineer and directly drive the original display.
