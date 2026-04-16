# ⚡ Electrical BOM (BLDC Generator System)

## Overview

This BOM covers the **essential electrical components** required to convert 3-phase AC from the BLDC motor into usable DC power.

---

# 📦 Bill of Materials

| Item | Component                     | Specification                           | Qty       | Notes                           |
| ---- | ----------------------------- | --------------------------------------- | --------- | ------------------------------- |
| 1    | 3-Phase Rectifier Module      | 200–600V, 20–30A, 5-pin (U, V, W, +, −) | 1         | Example: SBR2502G or equivalent |
| 2    | Bulk Capacitor (Electrolytic) | 3300–4700 µF, ≥100V                     | 1–2       | Main DC smoothing               |
| 3    | Fuse                          | 5A, DC rated                        | 1         | Protects downstream electronics |
| 4    | Buck Converter (DC-DC)        | Input ≥60–80V, Output 12V (or desired)  | 1         | For usable output               |
| 5    | TVS Diode (optional)          | ~70–75V clamp                           | 1         | Protects against voltage spikes |
| 6    | NTC Thermistor (optional)     | Inrush current limiter                  | 1         | Reduces startup surge           |
| 7    | Wiring (Power)                | 16–18 AWG silicone wire                 | As needed | For AC + DC paths               |
| 8    | Terminal Blocks / Connectors  | ≥100V, ≥10A rated                       | As needed | For clean connections           |
| 9    | Heatsink / Mount Plate        | Aluminum plate or heatsink              | 1         | For rectifier cooling           |

--- 

## ⚡3-Phase Rectifier Specification Summary

| Parameter            | Value                          |
| -------------------- | ------------------------------ |
| Input Source         | 3-phase BLDC motor (generator) |
| Input Voltage (AC)   | ~30–40V (line-to-line)         |
| Output Voltage (DC)  | ~50–65V                        |
| Max Voltage (spikes) | ~70–80V                        |
| Current              | ~2–3A                          |
| Power                | ~80–120W                       |


## ⚡Buck-Converter Requirements

| Parameter     | Required        |
| ------------- | --------------- |
| Input Voltage | ≥80–100V rating |
| Input Range   | wide (40–70V)   |
| Output        | 12V             |
| Current       | ≥5–6A           |
| Cooling       | REQUIRED        |
