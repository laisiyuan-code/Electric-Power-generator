# ⚡ 3-Phase Rectifier Design Calculator (BLDC Generator)

## Overview

This document provides a structured method to:

* Calculate requirements for a **3-phase rectifier**
* Size voltage and current ratings
* Select **commercially available rectifier modules**

Applicable for systems where a **BLDC motor is used as a generator**.

---

# 🧠 System Context

```text
BLDC Motor (Generator)
        ↓
3-Phase AC (U, V, W)
        ↓
3-Phase Rectifier
        ↓
DC Bus
        ↓
Regulator / Load
```

---

# 📥 Required Inputs

| Parameter         | Symbol | Unit       | Description                |
| ----------------- | ------ | ---------- | -------------------------- |
| Motor constant    | Kv     | V/1000 RPM | Back-EMF constant          |
| Max RPM           | N_max  | RPM        | Maximum operating speed    |
| Output power      | P_out  | W          | Expected electrical output |
| Efficiency (est.) | η      | -          | 0.7–0.85 typical           |

---

# ⚙️ Step 1: Calculate Maximum Voltage

## Formula

```text
V_phase = Kv × (RPM / 1000)
```

## Convert to DC bus voltage

For 3-phase rectification:

```text
V_DC ≈ 1.65 × V_phase
```

---

## Example

```text
Kv = 9.9 V/1000RPM
RPM = 4000

V_phase = 9.9 × 4 = 39.6V
V_DC ≈ 1.65 × 39.6 ≈ 65V
```

---

## Design Voltage

Always include safety margin:

```text
V_design = 1.2 – 1.5 × V_DC
```

### Recommended:

```text
V_design ≈ 80–100V
```

---

# ⚡ Step 2: Calculate Current

## Formula

```text
I = P_out / V_DC
```

---

## Example

```text
P_out = 100W
V_DC = 50V

I = 100 / 50 = 2A
```

---

## Design Current

Include margin:

```text
I_design = 2–3 × I
```

### Recommended:

```text
I_design ≈ 4–6A
```

---

# 🔥 Step 3: Rectifier Power Loss

Each conduction path has ~2 diode drops.

## Approximation

```text
V_drop ≈ 1.5–2V
```

## Power loss

```text
P_loss ≈ V_drop × I
```

---

## Example

```text
P_loss ≈ 2V × 3A = 6W
```

---

## Implication

* Rectifier must handle **thermal dissipation**
* Requires **heatsinking or airflow**

---

# 📊 Final Rectifier Specification

| Parameter      | Recommended Value             |
| -------------- | ----------------------------- |
| Type           | 3-phase full bridge           |
| Voltage rating | ≥200V                         |
| Current rating | ≥10–15A                       |
| Mounting       | Metal case (heat dissipation) |

---

# 🛒 Commercial Rectifier Selection Guide

## ✔ Voltage Rating

Choose:

```text
≥ 2 × maximum DC voltage
```

Example:

* System: 80V → choose **200V or higher**

---

## ✔ Current Rating

Choose:

```text
≥ 2–3 × expected current
```

Example:

* 3A system → choose **10A+ rectifier**

---

## ✔ Package Type

Preferred:

* Metal block rectifier
* Screw terminals
* Through-hole mounting

---

## ✔ Thermal Considerations

Ensure:

* Mount on metal plate OR
* Provide airflow

---

## ✔ Reliability Margin

Always overspec:

* Voltage spikes
* Load transients
* Engine RPM fluctuations

---

# ⚠️ Design Considerations

## 1. Voltage Spikes

* Sudden load removal → voltage surge
* Use **TVS diode** across DC bus

---

## 2. Ripple Voltage

Rectifier output is not smooth:

* Requires bulk capacitor
* Typical: **470–1000 µF (100V rated)**

---

## 3. Reverse Polarity Protection

Optional but recommended:

* diode or MOSFET protection stage

---

## 4. Thermal Stress

* Continuous operation generates heat
* Ensure adequate cooling

---

## 5. Overvoltage Risk

High RPM → high voltage:

* design for worst-case RPM
* do NOT rely on nominal values

---

# 🧠 Engineering Rules of Thumb

```text
Design for worst case, not average case
```

```text
Voltage rating ≥ 2× expected
```

```text
Current rating ≥ 2–3× expected
```

```text
Always include thermal margin
```

---

# 📈 Example Summary (Your System)

| Parameter      | Value        |
| -------------- | ------------ |
| Max RPM        | ~4000        |
| DC Voltage     | ~60–65V      |
| Design Voltage | ~80–100V     |
| Output Power   | ~100W        |
| Current        | ~2–3A        |
| Rectifier Spec | 200V, 10–15A |

---

# 🚀 Summary

To design a 3-phase rectifier:

1. Calculate voltage from RPM
2. Calculate current from power
3. Apply safety margins
4. Select commercially available module
5. Design for heat and transients

---

# Final Insight

> The rectifier is not just a converter — it is a **protection-critical component** that must survive worst-case operating conditions.
