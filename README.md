# RF Front-End Transmitter — BLE 2.4 GHz

Designed and simulated using **Cadence Virtuoso**

---

## Overview

A Bluetooth Low Energy (BLE) compatible RF front-end transmitter operating in the **2.4 GHz ISM band**, designed and verified using Cadence Virtuoso ADE with post-layout verification via Calibre.

---

## Architecture

```
Baseband Input (10 MHz)
        │
        ▼
  ┌─────────────┐     ┌─────┐
  │ Active Mixer│◄────│ VCO │  (2.4 GHz LC-tank oscillator)
  └─────────────┘     └─────┘
        │
        ▼
  ┌──────────────────┐
  │ Voltage Amplifier│
  └──────────────────┘
        │
        ▼
  ┌────────────────┐
  │ Power Amplifier│  (Class A, 2.41 GHz)
  └────────────────┘
        │
        ▼
    Antenna (50 Ω)
```

---

## Key Specifications

| Parameter | Value |
|---|---|
| Frequency Band | 2400 – 2483.5 MHz (ISM) |
| Modulation | GFSK (BLE) |
| Output Frequency | 2.435 GHz |
| Output Voltage | 318.28 mV |
| Output Current | 6.37 mA |
| RF Output Power | ~2.03 mW |
| Total DC Power | 8.925 mW |
| Efficiency | ~22.7% |
| Supply Voltage | 0.9 V |

---

## Building Blocks

### 1. Gilbert Cell Active Mixer
- Double-balanced CMOS Gilbert cell
- Conversion Gain: −0.4 dB
- Noise Figure: 8.56 dB (schematic), 8.69 dB (post-layout)
- IIP3: 0.505 dBm | OIP3: 0.486 dBm
- Power Consumption: 0.312 mW

### 2. Voltage Controlled Oscillator (VCO)
- LC-tank cross-coupled oscillator
- Oscillation Frequency: ~2.425 GHz
- Inductance: 8 nH

### 3. Voltage Amplifier
- Differential input, single-ended output
- Bandwidth: 7.94 GHz (pre-layout), 4.56 GHz (post-layout)
- IIP3: 6 dBm | OIP3: 20 dBm

### 4. Power Amplifier
- Class A CMOS, single-input single-output
- Operating Frequency: 2.41 GHz
- Optimum Load: 100 Ω → matched to 50 Ω
- Output Power: ~1.48 mW (post-layout)
- PAE: ~35%
- IP1dB: 11 dBm | OP1dB: 22.8 dBm

---

## Tools Used

- **Cadence Virtuoso** — Schematic design & simulation (ADE)
- **Calibre** — DRC, LVS, PEX (parasitic extraction)

---

## Results Summary

| Stage | Pre-layout | Post-layout |
|---|---|---|
| Mixer CG | 0.955 | 0.981 |
| Mixer NF | 8.56 dB | 8.69 dB |
| VCO Frequency | 2.425 GHz | ~2.44 GHz |
| Amp Bandwidth | 7.94 GHz | 4.56 GHz |
| PA Output Power | 2.13 mW | 1.48 mW |
| TX Output Power | 2.24 mW | 2.03 mW |
| TX Efficiency | — | 22.7% |

---

## References

- B. Razavi, *RF Microelectronics*, 2nd ed., Prentice Hall, 2012
- T. L. Vivek, M.Tech Thesis, *Analog Front-End Design of Bluetooth Transmitter*, IIT Madras, 2013
- S. P. Raajhen et al., *Design of Digital RF Transmitter for Bluetooth Applications*, ICCTET 2013

---
