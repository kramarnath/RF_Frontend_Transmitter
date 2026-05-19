# RF Front-End Transmitter — 2.4 GHz BLE

Final year B.Tech ECE project | GEC Thrissur

---

## What is this?

When you connect your phone to a Bluetooth speaker, your phone needs to convert its digital audio data into a radio signal and broadcast it through the air. The circuit that does this job is called an **RF Front-End Transmitter**.

This project designs and simulates exactly that — a small transmitter circuit that takes a low-frequency digital signal and converts it into a **2.4 GHz radio signal** compatible with Bluetooth Low Energy (BLE).

The entire design was built and tested virtually using **Cadence Virtuoso**, an industry-standard chip design tool.

---

## How does it work? (Simple version)

Think of it like a radio station in miniature:

1. **You start with your data** — a slow 10 MHz signal (your "voice")
2. **The VCO creates a carrier wave** — a fast 2.4 GHz signal (the "radio frequency")
3. **The Mixer combines them** — stamps your data onto the carrier wave
4. **The Voltage Amplifier boosts the signal** — makes it strong enough for the next stage
5. **The Power Amplifier cranks it up** — pushes it to transmission power
6. **Out through the antenna** — broadcasts as a Bluetooth radio wave

---

## Key Numbers

| What | Value |
|---|---|
| Output Frequency | 2.435 GHz (BLE band) |
| Input Signal | 10 MHz, 20 mV |
| Output Power | ~2 mW |
| Supply Voltage | 0.9 V |
| Total Power Used | 8.9 mW |
| Efficiency | 22.7% |

---

## Tools

- **Cadence Virtuoso** — circuit design and simulation
- **Calibre** — layout verification and parasitic extraction

---

For full technical details, see [`Documents/project_summary.md`](Documents/project_summary.md)
