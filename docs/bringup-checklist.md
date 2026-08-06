# Hardware Notes (Consolidated)

## 1. MCU Package and Soldering
- Target MCU package: **UFQFPN48** (STM32G431).
- Package characteristics:
  - Pads under body edge (no gull-wing leads)
  - Exposed thermal pad in center
- Assembly advice:
  - Prefer SMT assembly service if available.
  - If hand-soldering: use hot air (typically ~330-350°C, medium-low airflow), good flux, and solder paste.
  - For exposed pad (EP): small paste dots (not full flood) to avoid floating/shorts.
- Post-solder must-check:
  - Measure resistance between 3V3 and GND before first power-on.

## 2. Buck Stage (LM2596)
### 2.1 Schottky diode (1N5822)
- Polarity:
  - Stripe side = **Cathode (K)**
  - Non-stripe side = **Anode (A)**
- Required connection:
  - **K -> SW node**
  - **A -> GND**
- Critical rule:
  - If silkscreen conflicts with electrical net, trust schematic/netlist and multimeter continuity.

### 2.2 Inductor
- Selected model: **CDRH127/LDNP-330MC**
- Key parameters:
  - 33uH nominal
  - 12x12mm body
  - DCR around 53.3mΩ (max, per earlier reference)
  - Rated current around 3.9A class
- Mechanical caveat:
  - Height approx 8mm (check enclosure clearance).
- Layout caveat:
  - Confirm datasheet-recommended land pattern vs PCB footprint.

## 3. Capacitors
### 3.1 Small decoupling caps
- 0603 X7R preferred.
- Typical values used:
  - 100nF (multiple)
  - 10nF
  - 0.47uF

### 3.2 Bulk electrolytic caps
- Values observed in design:
  - 47uF
  - 100uF
  - 220uF
- Recommendations:
  - Low-ESR parts preferred for LM2596 stability/ripple performance.
  - Use sufficient voltage rating (commonly 16V/25V; input side may need 25V/35V depending VIN).
  - 220uF at 6.3x5.4 package may have limited options; enlarge package if needed.

## 4. Resistor Note (R4)
- Footprint appears to be **0402 (1005 Metric)**.
- Current net label suggests VBAT-to-PB4 path; verify design intent in schematic.
- Final resistance value still TBD before purchasing final BOM.

## 5. First Power-On Safety
- Use bench supply current limit: **0.1A~0.2A** for initial test.
- Bring-up sequence:
  1. Continuity/short checks
  2. Low-current power-on
  3. Verify output rails
  4. Thermal check by touch/IR
  5. Increase limit gradually
