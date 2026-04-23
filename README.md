# 1. Introduction

## Background
Portable electrical power is important for outdoor activities such as camping, hiking support setups, emergency use, and remote work in off-grid locations. Many common devices used during camping, including phones, lights, GPS units, fans, and small USB-powered electronics, depend on a stable DC power source. In locations where there is no wall socket or mains supply, an independent portable generator system can help provide electrical energy on demand.

This project is based on the *Electric-Power-generator* repository, which explores a concept where rotational mechanical energy drives a brushless DC (BLDC) motor used as a generator. The generated 3-phase AC output is then rectified and smoothed into DC power using a rectifier module and capacitor bank, before being stepped down through a buck converter into a usable output voltage. The repository lists key electrical subsystems including a 3-phase rectifier, smoothing capacitor, fuse, buck converter, optional TVS diode, optional NTC thermistor, power wiring, connectors, and heatsinking. :contentReference[oaicite:1]{index=1}

## Problem Statement
When camping or travelling in remote outdoor areas, power sockets are often unavailable. This makes it difficult to charge essential low-power devices such as mobile phones, LED lights, or small electronics. A portable generator that converts mechanical motion into usable DC electrical power can provide a practical off-grid energy source.

## Objective of the Project
The objective of this project is to develop and evaluate a compact portable power-generation concept that converts mechanical rotational input into regulated DC electrical output suitable for outdoor use. The project aims to:
- generate electrical power from a rotating generator stage,
- convert the generator's 3-phase AC output into DC,
- smooth and regulate the output into a useful voltage,
- assess whether the design is suitable for portable off-grid scenarios such as camping.

## Scope of the Report
This report focuses on the electrical power generation stage described in the repository. It covers the design requirements, system concept, operating principle, component selection, calculations, prototype implementation approach, testing strategy, and evaluation of performance. Since the repository itself notes that the RC engine version is high-risk and not recommended as a first build, this report treats the concept primarily as a technical study and emphasizes the safer low-voltage bench-prototype approach for validation. 


# ⚡ Electrical BOM (BLDC Generator System)

## Overview

This BOM covers the **essential electrical components** required to convert 3-phase AC from the BLDC motor into usable DC power.

---

# 📦 Bill of Materials

| Item | Component                     | Specification                           | Qty       | Notes                           |
| ---- | ----------------------------- | --------------------------------------- | --------- | ------------------------------- |
| 1    | 3-Phase Rectifier Module      | 200–600V, 20–30A, 5-pin (U, V, W, +, −) | 1         | Example: SBR2502G or equivalent |
| 2    | Bulk Capacitor (Electrolytic) | 3300–4700 µF, ≥100V                     | 1–2       | Main DC smoothing               |
| 3    | Fuse                          | 5A–10A, DC rated                        | 1         | Protects downstream electronics |
| 4    | Buck Converter (DC-DC)        | Input ≥60–80V, Output 12V (or desired)  | 1         | For usable output               |
| 5    | TVS Diode (optional)          | ~70–75V clamp                           | 1         | Protects against voltage spikes |
| 6    | NTC Thermistor (optional)     | Inrush current limiter                  | 1         | Reduces startup surge           |
| 7    | Wiring (Power)                | 16–18 AWG silicone wire                 | As needed | For AC + DC paths               |
| 8    | Terminal Blocks / Connectors  | ≥100V, ≥10A rated                       | As needed | For clean connections           |
| 9    | Heatsink / Mount Plate        | Aluminum plate or heatsink              | 1         | For rectifier cooling           |
