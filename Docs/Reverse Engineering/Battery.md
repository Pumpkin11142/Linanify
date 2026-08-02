# iPod Nano 1st Generation Battery

## Overview

The 1st generation iPod Nano uses a single-cell lithium polymer (Li-Po) battery pack.

The battery is a rechargeable lithium-ion chemistry pouch cell with integrated protection circuitry. Charging and power management are handled by circuitry on the iPod motherboard.

---

# Known Specifications

| Parameter           | Value                             | Notes                                                 |
| ------------------- | --------------------------------- | ----------------------------------------------------- |
| Chemistry           | Lithium-ion Polymer (Li-Po)       | Common pouch cell construction                        |
| Nominal Voltage     | 3.7V                              | Standard single-cell Li-ion voltage                   |
| Full Charge Voltage | 4.2V                              | Standard Li-ion charge termination voltage            |
| Typical Capacity    | ~300mAh                           | Original 1st generation Nano batteries vary slightly  |
| Cell Count          | 1S                                | Single cell battery                                   |
| Connector           | Soldered battery leads            | Exact connection method varies by replacement battery |
| Protection          | Battery pack protection circuitry | Prevents overcharge, over-discharge, and over-current |

---

# Charging

Charging is managed by the iPod's internal power management circuitry.

Known charging behavior:

* Lithium batteries use CC/CV charging.
* Charging begins with constant current.
* Charging transitions to constant voltage near 4.2V.
* Charging terminates when current falls below a threshold.

The exact charging parameters are controlled by the motherboard charging IC.

---

# Reverse Engineering Notes

## Known

* Battery voltage: approximately 3.7V nominal.
* Battery is a single-cell Li-ion polymer pack.
* Battery connects directly to the motherboard.

## Unknown

* Exact original battery model number.
* Original battery internal resistance.
* Exact protection IC used inside the battery pack.

## Measurements Needed

* Battery cavity dimensions.
* Maximum replacement battery thickness.
* Available battery capacity increase possible with redesigned PCB.

---

# Linanify Design Considerations

Potential improvements:

* Use a physically larger modern Li-Po cell if space allows.
* Add proper battery monitoring hardware.
* Add fuel gauge IC for accurate percentage reporting.
* Design battery connector for easier replacement.

Safety:

Never charge a Li-ion battery directly without proper charging and protection circuitry.
