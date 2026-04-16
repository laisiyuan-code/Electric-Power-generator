# ⚙️ System Output Table (RC Engine → BLDC Generator)

## 🧠 Assumptions

| Parameter             | Value               |
| --------------------- | ------------------- |
| Engine Speed          | 25,000 – 30,000 RPM |
| Total Reduction Ratio | 7.5 : 1             |
| Motor Kv              | 9.9 V / 1000 RPM    |
| System Efficiency     | ~70–80%             |

---

# 📊 Output Across Operating Range

| Engine RPM | Motor RPM | AC Voltage (V_phase) | DC Voltage (V_DC) | Estimated Power (W) | Current @ DC (A) |
| ---------- | --------- | -------------------- | ----------------- | ------------------- | ---------------- |
| 25,000     | 3,330     | 33.0 V               | ~54 V             | ~90–110 W           | ~1.7–2.2 A       |
| 27,000     | 3,600     | 35.6 V               | ~59 V             | ~100–120 W          | ~1.7–2.1 A       |
| 28,000     | 3,730     | 36.9 V               | ~61 V             | ~105–125 W          | ~1.7–2.0 A       |
| 30,000     | 4,000     | 39.6 V               | ~65 V             | ~110–140 W          | ~1.7–2.2 A       |

---

# ⚙️ Calculation Notes

## Motor Speed

```text
Motor RPM = Engine RPM / 7.5
```

---

## AC Voltage (from motor)

```text
V_phase = Kv × (RPM / 1000)
```

---

## DC Voltage (after rectifier)

```text
V_DC ≈ 1.65 × V_phase
```

---

## Current

```text
I = P / V
```

---

# 🔥 Key Observations

* System now operates at **higher voltage (54–65V DC)**
* At **30k RPM**, motor hits ~4000 RPM → **upper safe limit**
* Output power increases but **thermal load also increases**
* Current remains low → wiring stays manageable

---

# ⚠️ Critical Insight

> At 30k RPM, you are at the **edge of safe motor speed and voltage**

* Voltage spikes may exceed **70V**
* Ensure:

  * **≥100V capacitors**
  * **≥200V rectifier (you already have)**
  * good cooling

---

# 🚀 Summary

> Your system produces **~55–65V DC at ~90–140W** in the 25k–30k RPM range, operating near the motor’s upper safe limits.
