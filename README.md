# STM32G431 + LM2596 Custom Board

## Project Status
- PCB design completed
- Assembly not started yet

## Goals
- Build a custom control/power board based on STM32G431.
- Use LM2596 buck stage for stable DC conversion.
- Complete bring-up with safe current-limited power-on.

## Confirmed Hardware Decisions
- MCU: **STM32G431** (UFQFPN48 package)
- Buck IC: **LM2596S-ADJ**
- Schottky diode: **1N5822**
  - Polarity rule: **K (stripe) -> SW**, **A -> GND**
- Inductor: **CDRH127/LDNP-330MC**
  - 33uH, 12x12mm footprint, height ~8mm
- Small capacitors (SMD): 0603, X7R preferred
- R4 package: 0402 (1005 Metric), value TBD by final schematic intent

## Current Risks / Open Items
- [ ] Verify D2 pad net with multimeter (must be SW/GND as expected)
- [ ] Confirm 8mm inductor height clearance with enclosure/mechanics
- [ ] Confirm 220uF capacitor package availability (6.3x5.4 may be tight)
- [ ] Finalize R4 resistance value
- [ ] Prepare first power-on with current limit (0.1A~0.2A)

## Repository Layout
- `docs/`: notes, checklist, images
- `hardware/kicad/`: source schematic + PCB
- `hardware/fabrication/`: gerber, drill, BOM, pick-and-place
- `hardware/datasheets/`: key PDFs
- `firmware/`: future STM32 firmware

## First Bring-Up (Summary)
1. Visual inspection (orientation, bridges, polarity)
2. Resistance checks (VIN-GND, 5V-GND/3V3-GND)
3. Power from bench supply with 0.1A current limit
4. Verify LM2596 output and thermal behavior
5. Increase current limit gradually

## Notes
- UFQFPN48 is difficult for hand soldering; hot-air and flux are strongly recommended.
- Always trust actual net connectivity + multimeter over silkscreen when conflict exists.
