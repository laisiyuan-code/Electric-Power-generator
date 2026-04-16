# 🔒 Protection Design (Fuse / Circuit Breaker)

## 🧠 System Reference

| Parameter      | Value   |
| -------------- | ------- |
| DC Voltage     | ~50–65V |
| Max Voltage    | ~70–80V |
| Normal Current | ~2–3A   |
| Peak Current   | ~4–5A   |

---

# ⚙️ Fuse Sizing Calculation

## Rule

```text
Fuse Rating = 1.5× to 2× normal current
```

---

## Your System

```text
Normal current ≈ 2–3A
```

```text
Fuse ≈ 3A – 6A
```

---

## ✅ Final Selection

```text
Recommended: 5A fuse
Type: Slow-blow (T-type)
```

---

# ⚡ Why Slow-Blow?

Startup behaviour:

```text
Capacitor charging → high inrush current spike
```

Slow-blow fuse:

* tolerates short spikes
* still protects against sustained faults

---

# 📍 Fuse Placement

```text
Rectifier (+) → Fuse → Capacitor → Load
```

👉 Always protect the **DC side**

---

# 🔥 Circuit Breaker Option

## When to use

* reusable protection
* testing / debugging
* frequent resets expected

---

## Recommended Spec

```text
DC-rated breaker
5A – 6A
≥100V DC rating
```

---

# ⚠️ Critical Design Rules

## 1. Do NOT oversize

```text
Too large → no protection
```

Example:

* 13A fuse ❌ (will not trip in fault)

---

## 2. Match voltage rating

```text
Fuse voltage ≥ system max voltage
```

Use:

```text
≥100V DC rated fuse
```

---

## 3. Protect wiring, not just components

Fuse should trip **before wires overheat**

---

## 4. Account for transients

System has:

* RPM spikes
* load changes
* capacitor inrush

👉 Requires margin + slow-blow behaviour

---

# 📊 Summary

| Item           | Spec            |
| -------------- | --------------- |
| Fuse Rating    | 5A              |
| Type           | Slow-blow       |
| Voltage Rating | ≥100V DC        |
| Placement      | After rectifier |
| Alternative    | 5–6A DC breaker |

---

# 🚀 One-Line Summary

> Use a **5A slow-blow fuse on the DC side** to protect against faults while tolerating startup surges.
