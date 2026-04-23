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

# 2. Design Requirements / Specifications

The system requirements are derived from the intended use case of portable off-grid power generation for camping, together with the electrical architecture described in the repository.

| Category | Requirement / Specification |
|---|---|
| Required Input | Rotational mechanical input to drive a BLDC motor as generator |
| Generator Output | 3-phase AC output from BLDC generator |
| Electrical Conversion | Rectification from 3-phase AC to DC |
| DC Smoothing | Bulk capacitor of approximately 3300–4700 µF, rated at ≥100 V |
| Usable Output | Regulated DC output via buck converter, for example 12 V or another desired DC level |
| Protection | Fuse rated about 5–10 A on DC side |
| Optional Protection | TVS diode for voltage spikes; NTC thermistor for inrush-current limiting |
| Wiring / Connectors | Power wiring around 16–18 AWG; connectors rated ≥100 V and ≥10 A |
| Thermal Requirement | Rectifier should be mounted to an aluminium plate or heatsink |
| Performance Target | Produce stable regulated DC output from variable-speed generator input |
| Safety Requirement | Avoid unstable voltage, overheating, battery charging faults, hot surfaces, vibration issues, and exposed rotating parts |
| Cost / Practicality | Use readily available power electronics modules and standard wiring components |

### System Constraints
- Generator voltage varies with rotational speed and electrical load.
- Raw output is not directly usable and must be rectified and regulated.
- A fuel-powered RC engine implementation introduces significant mechanical, thermal, fire, vibration, and electrical risks.
- The repository recommends a low-voltage motor-driven bench prototype before attempting any fuel-powered version. 

# 3. System Design / Methodology

## Overall Design Concept
The overall concept is to convert mechanical rotational energy into electrical energy using a BLDC motor operated as a generator. The generator produces 3-phase AC, which is then passed through a rectifier module to obtain DC. A bulk capacitor smooths the rectified voltage, while a buck converter regulates it down to a useful output voltage for loads such as USB-powered or 12 V devices.

## How the System Works
1. A prime mover provides rotational mechanical input.
2. The BLDC motor acts as a 3-phase generator.
3. The 3-phase AC output is connected to a rectifier module.
4. The rectified DC is smoothed using a high-value electrolytic capacitor.
5. Protective devices such as a fuse, TVS diode, and NTC thermistor can be added.
6. A DC-DC buck converter regulates the smoothed DC to the desired output voltage.
7. The regulated output powers the load.

## Why These Components Were Chosen
- **BLDC motor as generator:** convenient way to obtain 3-phase AC from rotational motion.
- **3-phase rectifier module:** converts variable AC to DC using a compact module.
- **Bulk capacitor:** reduces ripple after rectification.
- **Fuse:** protects downstream electronics from overcurrent.
- **Buck converter:** steps variable DC down to a usable stable voltage.
- **TVS diode:** helps clamp transient voltage spikes.
- **NTC thermistor:** reduces startup surge current.
- **Heatsink / aluminium plate:** improves heat dissipation from the rectifier. :contentReference[oaicite:4]{index=4}

## Block Diagram

```text
Mechanical Input
      ↓
BLDC Motor Used as Generator
      ↓
3-Phase AC Output (U, V, W)
      ↓
3-Phase Rectifier Module
      ↓
Smoothed DC Bus + Bulk Capacitor
      ↓
Protection Stage (Fuse / TVS / NTC)
      ↓
Buck Converter
      ↓
Regulated DC Output
      ↓
Lead Acid Battery / Portable Camping Load
```


# 4. Equations / Calculations / Technical Analysis

For further details on calculations, please check out :
1. **3-Phase Rectifier Design Calculator**
2. **Buck-Converter-Calculation**
3. **Safety-Considerations**
4. **System Output** 

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
