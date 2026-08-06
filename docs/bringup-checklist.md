# Bring-Up Checklist (STM32G431 + LM2596)

## A. Pre-Solder Checklist
- [ ] All parts received and matched with BOM values
- [ ] Verify package compatibility (especially inductor and electrolytics)
- [ ] Confirm orientation marks for:
  - [ ] STM32 pin-1
  - [ ] 1N5822 stripe side
  - [ ] Electrolytic capacitor polarity
- [ ] Flux, paste, tweezers, hot-air station ready

## B. Post-Solder Visual Inspection
- [ ] No solder bridges on MCU pins
- [ ] Exposed pad not over-pasted (no floating package)
- [ ] Diode direction correct (K->SW, A->GND)
- [ ] Electrolytic caps polarity correct
- [ ] Inductor seated and aligned
- [ ] No missing passives

## C. Multimeter Checks (Power OFF)
- [ ] VIN to GND resistance (not near-short)
- [ ] 5V/3V3 to GND resistance (not near-short)
- [ ] Continuity check D2 pad-to-net:
  - [ ] Stripe pad continuity to SW node
  - [ ] Other pad continuity to GND

## D. First Power-On (Bench Supply)
- [ ] Set current limit to 0.1A
- [ ] Start with intended VIN (or lower safe VIN if design allows)
- [ ] Confirm current does not instantly clamp hard
- [ ] Measure LM2596 output voltage
- [ ] If normal, raise current limit gradually to 0.2A / 0.3A
- [ ] Check temperature of LM2596, diode, inductor

## E. MCU Bring-Up
- [ ] Confirm 3V3 stable
- [ ] SWD connection recognized
- [ ] Flash minimal test firmware (blinky/UART log)
- [ ] Verify reset/boot behavior

## F. If Abnormal
- [ ] Immediate power-off
- [ ] Re-check shorts and polarity
- [ ] Inspect suspicious joints with magnification
- [ ] Reflow MCU/diode region if needed

  1. Continuity/short checks
  2. Low-current power-on
  3. Verify output rails
  4. Thermal check by touch/IR
  5. Increase limit gradually
