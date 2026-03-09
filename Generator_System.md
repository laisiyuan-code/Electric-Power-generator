# RC Engine Generator Concept Review

## Project Status
This concept is **not recommended as a first build**.

Using a nitro RC engine to drive a brushless motor as a generator introduces several hazards at the same time:

- high-speed rotating parts
- hot exhaust and engine surfaces
- flammable fuel
- vibration and mechanical imbalance
- unregulated electrical output

Because of that, this repository should be treated as a **concept evaluation and safety review**, not a build guide.

---

## Why This Is High Risk

### Mechanical Risk
RC nitro engines operate at very high RPM. Any pulley, coupler, clutch, or shaft misalignment can lead to:

- thrown belts
- shaft whip
- bearing failure
- detached rotating parts

### Thermal and Fire Risk
The engine and exhaust become hot during operation, while the system also stores fuel nearby.

Risks include:

- burns
- ignition of nearby materials
- fuel leakage near hot engine parts

### Electrical Risk
A brushless motor used as a generator produces 3-phase output that varies with speed and load.

This means the system can produce:

- unstable voltage
- unexpected voltage spikes
- overheating in the rectifier or regulator
- battery charging faults if regulation is poor

---

## Recommended Safer Alternative

Before attempting any fuel-powered version, prototype the generator stage using a **low-voltage electric prime mover** instead.

### Safer Bench Prototype
Use:

- a DC motor or low-voltage brushless motor as the driver
- a second brushless motor as the generator
- a current-limited bench power supply
- a low-voltage rectifier and regulator stage
- a guarded test stand

### Why This Is Better
This lets you validate:

- generator output versus RPM
- rectification behavior
- regulator heating
- battery-charging or load behavior
- mounting stiffness and vibration response

without introducing fuel, combustion, and extreme RPM immediately.

---

## Suggested Repository Structure

```text
rc-engine-generator/
├── README.md
├── docs/
│   ├── 01_project_scope.md
│   ├── 02_risk_assessment.md
│   ├── 03_test_plan.md
│   ├── 04_bench_prototype.md
│   └── 05_future_engine_version.md
├── images/
│   └── concept_block_diagram.png
└── data/
    └── test_results.csv
