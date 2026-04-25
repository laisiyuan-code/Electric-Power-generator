# 1. Introduction

## Background
Portable electrical power is important for outdoor activities such as camping, hiking support setups, emergency use, and remote work in off-grid locations. Many common devices used during camping, including phones, lights, GPS units, fans, and small USB-powered electronics, depend on a stable DC power source. In locations where there is no wall socket or mains supply, an independent portable generator system can help provide electrical energy on demand.

This project explores a concept where rotational mechanical energy drives a brushless DC (BLDC) motor used as a generator. The generated 3-phase AC output is then rectified and smoothed into DC power using a rectifier module and capacitor bank, before being stepped down through a buck converter into a usable output voltage. The repository lists key electrical subsystems including a 3-phase rectifier, smoothing capacitor, fuse, buck converter, optional TVS diode, optional NTC thermistor, power wiring, connectors, and heatsinking.

## Problem Statement
When camping or travelling in remote outdoor areas, power sockets are often unavailable. This makes it difficult to charge essential low-power devices such as mobile phones, LED lights, or small electronics. A portable generator that converts mechanical motion into usable DC electrical power can provide a practical off-grid energy source.

## Objective of the Project
The objective of this project is to develop and evaluate a compact portable power-generation concept that converts mechanical rotational input into regulated DC electrical output suitable for outdoor use. The project aims to:
- generate electrical power from a rotating generator stage,
- convert the generator's 3-phase AC output into DC,
- smooth and regulate the output into a useful voltage,
- assess whether the design is suitable for portable off-grid scenarios such as camping.

## Scope of the Report
This report focuses on the electrical power generation stage. It covers the design requirements, system concept, operating principle, component selection, calculations, prototype implementation approach, testing strategy, and evaluation of performance. Note that the RC engine version is high-risk and not recommended as a first build, but this report treats the concept primarily as a technical study and emphasizes the safer low-voltage bench-prototype approach for validation. 

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

For further details on calculations and technical requirements, please check out :
1. **3-Phase Rectifier Design Calculator**
2. **Buck-Converter-Calculation**
3. **Electrical-Requirements**
4. **Safety-Considerations**
5. **System Output** 

# ⚡ Electrical Block Diagram (BLDC Generator System)

## Overview

This section covers the overall flow of electrical components required to convert 3-phase AC from the BLDC motor into usable DC power.

# Block Diagram
<img width="1024" height="768" alt="EPS_BlockDiagram" src="https://github.com/user-attachments/assets/56d7f486-58b0-4813-a9c1-9b1005c0224a" />

# ⚡⚡ 3 Phase Rectifier Design

For this project, a custom 3 phase rectifier was designed to properly fit within the system and work for the intended purpose

<p align="center">
  <img width="700" alt="3 Phase Full Bridge Rectifier Schematic" src="https://github.com/user-attachments/assets/71cf7123-3b1b-493a-95d2-15b34866a1b6" />
</p>
<p align="center">
  <em>Figure 1: 3 Phase Full Bridge Rectifier schematic.</em>
</p>

<p align="center">
  <img width="700" alt="3 Phase Full Bridge Rectifier Board Design" src="https://github.com/user-attachments/assets/06712d1f-bed3-4e11-850c-51d1665d077f" />
</p>
<p align="center">
  <em>Figure 2: 3 Phase Full Bridge Rectifier PCB board design.</em>
</p>

<table align="center">
  <tr>
    <td align="center">
      <img width="400" alt="3 Phase Full Bridge Rectifier Physical Board Top" src="https://github.com/user-attachments/assets/83b25985-a1a5-4eb3-97b0-1862d66ec1e9" />
      <br>
      <em>Figure 3: Physical PCB top view.</em>
    </td>
    <td align="center">
      <img width="400" alt="3 Phase Full Bridge Rectifier Physical Board Bottom" src="https://github.com/user-attachments/assets/77101d33-5dfb-4f64-b41b-856268805363" />
      <br>
      <em>Figure 4: Physical PCB bottom view.</em>
    </td>
  </tr>
</table>

# 🔧 Mechanical Breakdown

The mechanical system is designed to hold the engine, transmission stage, and BLDC generator in a fixed alignment so that rotational power can be transferred from the engine to the motor through a multi-stage timing belt reduction system.

The overall mechanical assembly is built around an aluminium profile frame. This frame provides the main structural base and allows the different mounts to be positioned, adjusted, and secured during assembly.

<p align="center">
  <img width="700" alt="Mechanical Assembly Isometric View" src="https://github.com/user-attachments/assets/b837fbdd-9aed-4159-94d9-0abc69a3781e" />
</p>
<p align="center">
  <em>Figure 5: Full mechanical assembly isometric view.</em>
</p>


## Main Mechanical Structure

The frame begins with aluminium profiles arranged to form the general shape of the generator structure. These profiles act as the main support rails for the engine, motor, and transmission system.

The aluminium profiles are held together using brackets and horizontal spacers. The brackets provide rigid corner and side connections, while the horizontal spacers maintain the correct separation between the profiles and improve the stiffness of the frame.

<table align="center">
  <tr>
    <td align="center">
      <img width="500" alt="Horizontal Spacer" src="https://github.com/user-attachments/assets/14e6c144-5010-4ff9-afea-9c74717a7653" />
      <br>
      <em>Figure 6: Horizontal spacer used to maintain frame spacing and rigidity.</em>
    </td>
    <td align="center">
      <img width="500" alt="Frame Bracket" src="https://github.com/user-attachments/assets/7cb6a5a2-7acb-423f-b89a-6f750a9c7b05" />
      <br>
      <em>Figure 7: Bracket used to connect and reinforce the aluminium profile frame.</em>
    </td>
  </tr>
</table>


## Main Components Connected to the Frame

There are four main mechanical groups attached to the aluminium profile frame:

| Component Group | Purpose |
|---|---|
| Aluminium profile frame | Main structural base of the system |
| STS GT .21 engine mount | Holds the engine securely to the frame |
| 57BYA94-48-01 BLDC motor mount | Holds the BLDC motor in position as the generator |
| 3-stage transmission mount | Supports the pulley shafts and gear-reduction stages |

## Engine Mount

The STS GT .21 engine is mounted to the aluminium profile frame using a dedicated engine-to-aluminium-profile mount. This part allows the engine to be fixed to the frame while keeping the engine shaft aligned with the first pulley stage.

<p align="center">
  <img width="500" alt="Engine to Aluminium Profile Mount" src="https://github.com/user-attachments/assets/690c53a3-0c97-45e8-89d7-760dad1b7239" />
</p>
<p align="center">
  <em>Figure 8: Engine-to-aluminium-profile mount for securing the STS GT .21 engine.</em>
</p>

The engine mount is important because the first pulley is directly connected to the engine output. If the engine is not mounted rigidly, the timing belt may slip, vibrate, or misalign during rotation.

## BLDC Motor Mount

The 57BYA94-48-01 BLDC motor is mounted using a dedicated motor mount. In this system, the BLDC motor acts as the generator. When the motor shaft is rotated by the transmission system, it produces a 3-phase AC electrical output.

<p align="center">
  <img width="500" alt="BLDC Motor Mount" src="https://github.com/user-attachments/assets/d4f90d41-8c6e-4b59-b48c-202222efcd69" />
</p>
<p align="center">
  <em>Figure 9: BLDC motor mount for securing the 57BYA94-48-01 motor.</em>
</p>

The motor mount keeps the generator shaft aligned with the final pulley stage. Proper alignment is important because the final belt connection transfers the reduced-speed, higher-torque rotation into the motor shaft.

## Gear Reduction Stage Mount

The 3-stage transmission system is supported by the gear reduction stage mount. This mount holds the intermediate shafts and pulleys used to transfer rotation from the engine to the BLDC motor.

<p align="center">
  <img width="500" alt="Gear Reduction Stage Mount" src="https://github.com/user-attachments/assets/06edfa8f-9b72-4896-849a-a42d529f1913" />
</p>
<p align="center">
  <em>Figure 10: Gear reduction stage mount used to support the intermediate pulley shafts.</em>
</p>

The purpose of the transmission is to step down the high-speed rotation from the engine before it reaches the BLDC motor. This makes the mechanical system easier to control and helps match the engine output to the generator input.

## Power Transmission Path

The rotation from the STS GT .21 engine is transferred to the BLDC motor through a timing belt and pulley system.

The transmission path is as follows:

```text
STS GT .21 Engine
    ↓
C-HTPA16S3M100-A-P5 pulley
    ↓ Timing belt
C-HTPA48S3M100-A-P10 pulley
    ↓ Same shaft
2 × C-HTPA25S3M100-A-P10 pulleys
    ↓ Timing belt
Set of C-HTPA25S3M100-A-P5 pulleys
    ↓ Same shaft
C-HTPA16S3M100-A-P5 pulley
    ↓ Timing belt
C-HTPA40S3M100-A-P8 pulley at BLDC motor
    ↓
57BYA94-48-01 BLDC Motor / Generator
