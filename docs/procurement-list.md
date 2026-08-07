# Procurement List (Current Draft)

## 1) Core ICs
- STM32G431 (UFQFPN48 package)
- LM2596S-ADJ
- 1N5822 (Schottky diode, DO-201 class)

## 2) Power Inductor
- Selected: **CDRH127/LDNP-330MC** (33uH, 12x12mm, H~8mm)

## 3) Capacitors (from current design snapshot)
- C1: 100nF, 0603, X7R
- C2: 0.47uF, 0603, X7R
- C3: 47uF, SMD electrolytic, low ESR
- C4: 100nF, 0603, X7R
- C5: 10nF, 0603, X7R
- C6: 100nF, 0603, X7R
- C7: 100nF, 0603, X7R
- C8: 100uF, SMD electrolytic, low ESR
- C9: 220uF, SMD electrolytic, low ESR
- C10: 100nF, 0603, X7R

## 4) Resistors
- R4 package: 0402 (1005 Metric), resistance value TBD
- Suggest stocking common debug values:
  - 0Ω
  - 100Ω
  - 10kΩ

## 5) Recommended Tools / Consumables
- Flux pen / solder paste
- Hot-air station
- Fine tweezers
- Multimeter
- Bench power supply with current limiting
- Optional oscilloscope (ripple/SW waveform check)

## 6) Pending Procurement Decisions
- Final R4 value after schematic intent confirmation
- Final electrolytic voltage rating vs actual VIN
- C9 package upsize if 6.3x5.4 sourcing is limited
