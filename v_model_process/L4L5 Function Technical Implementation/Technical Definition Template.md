# Technical Definition Template

*Use this optional template at Level 4 (L4) of the lightweight V-Model when a feature, calculation, circuit, or crafted piece requires exact numerical precision. The Technical Definition provides specific constants, calibration formulas, pinout maps, wire gauges, mix ratios, or data schemas that implement a parent Functional Definition. It provides the exact numbers and test vectors that Unit Testing verifies.*

---

# [Technical Definition Title]

- **Document ID:** TD-[XXX] (e.g., `TD-TEMP-01: Thermistor Calibration Constants & Schemas` or `TD-DRAIN-01: Mortar Mix & Liner Specifications`)
- **Parent Functional Definition:** [FD-XXX: Functional Definition Name]
- **Parent Component:** [CD-XXX: Component Name]
- **Parent Project:** [PD-XXX: Project Definition Name]
- **Author / Builder:** [Name]
- **Status:** [Draft | In Review | In Build / Fabrication | In Unit Testing | Complete]
- **Target Date:** [YYYY-MM-DD]

---

## 1. Technical Overview

*Provide a concise summary of the exact technical parameters defined here. State which Functional Definition this document implements and why precise specifications are required.*

- **Specification Scope:** [Summarize what this technical specification covers in 1–2 sentences.]
- **Target Implementation:** [Where this applies, e.g., Microcontroller firmware ADC routine, workbench custom PCB, or bathroom shower floor mortar bed.]

---

## 2. Exact Constants, Formulas & Specifications

*Define exact mathematical equations, conversion formulas, calibration coefficients, or material recipes. Every term must have clear units and bounds.*

### Mathematical Formulas / Conversion Equations
```
[e.g., 1 / T = A + B * ln(R) + C * (ln(R))^3]
```

- **Variables & Terms:**
  - `T`: [e.g., Temperature in Kelvin]
  - `R`: [e.g., Thermistor measured resistance in Ohms]
  - `A, B, C`: [Calibration constants specified in table below]

### Material Mix / Mechanical Specifications
- **Core Mixture / Material:** [e.g., 4 parts washed masonry sand to 1 part Portland cement by volume (dry-pack deck mud).]
- **Liquid Ratio / Consistency:** [e.g., Water added until handful packs into ball without weeping water (approx. 1/3 to 1/2 gallon per 60 lb mix).]
- **Dimensional Limits:** [e.g., Minimum mortar thickness 1/2 inch at drain; maximum 1-1/2 inches at perimeter corners.]

---

## 3. Physical, Electrical & Pin Mapping

*Specify physical pin numbers, wire gauges, terminal connections, or mechanical mounting points.*

| Signal / Joint Name | Pin / Channel / Location | Direction | Voltage / Rating / Gauge | Wire Color / Material | Description & Notes |
| --- | --- | --- | --- | --- | --- |
| **[Signal 1]** | [e.g., GPIO 0 / ADC 1] | Input | [0.0 to 3.3 V] | [Shielded twisted pair] | [Thermistor voltage divider tap] |
| **[Power Feed]** | [e.g., 3V3 / Pin 1] | Output | [3.3 V DC, 50 mA max] | [Red 24 AWG wire] | [Regulated power to sensor divider] |
| **[Ground]** | [e.g., GND / Pin 2] | Ground | [0 V reference] | [Black 24 AWG wire] | [Common sensor ground return] |
| **[Mechanical Joint]** | [e.g., Drain Flange] | Physical | [Schedule 40 PVC] | [Solvent welded] | [2-inch clamping drain connection] |

---

## 4. Data Formats & Communication Schemas (If Applicable)

*Specify exact payload layouts, JSON keys, topic naming conventions, or byte layouts for software and electronics projects.*

### Telemetry Payload Schema
```json
{
  "temp_c": 21.4,
  "battery_v": 3.82,
  "status": "OK"
}
```

| Field Name | Data Type | Unit | Range / Values | Required? | Description |
| --- | --- | --- | --- | --- | --- |
| `temp_c` | Float | °C | -20.0 to 60.0 | Yes | Filtered temperature reading |
| `battery_v` | Float | Volts | 2.50 to 4.25 | Yes | Measured cell terminal voltage |
| `status` | String | Enum | "OK", "WARN", "FAULT" | Yes | Operational health status |

---

## 5. Configuration Parameters & Tunable Constants

*List all named constants, calibration values, threshold numbers, and their default settings.*

| Parameter Name | Data Type / Unit | Default Value | Valid Range | Tunable at Runtime? | Description & Purpose |
| --- | --- | --- | --- | --- | --- |
| `CAL_COEFF_A` | Float | `1.129e-3` | Fixed | No | Steinhart-Hart primary coefficient |
| `CAL_COEFF_B` | Float | `2.341e-4` | Fixed | No | Steinhart-Hart secondary coefficient |
| `CAL_COEFF_C` | Float | `8.775e-8` | Fixed | No | Steinhart-Hart tertiary coefficient |
| `COOL_THRESHOLD_C` | Float (°C) | `18.0` | 10.0 to 30.0 | Yes | Alert trigger temperature differential |
| `FILTER_SAMPLES` | Integer | `5` | 3 to 10 | No | Number of ADC samples per wakeup |

---

## 6. Test Vectors (Executable Test Data)

*List concrete sample inputs and their exact expected outputs. Each row represents a direct unit test case.*

| Vector ID | Input Data / Condition | Expected Output / Value | Tolerance | Test Purpose |
| --- | --- | --- | --- | --- |
| **TV-01** | [Raw ADC count = 1850 (1.49 V)] | [Temperature = 21.5 °C] | [± 0.2 °C] | [Nominal room temperature test] |
| **TV-02** | [Raw ADC count = 3200 (2.58 V)] | [Temperature = 0.2 °C] | [± 0.2 °C] | [Freezing boundary point check] |
| **TV-03** | [Raw ADC count = 50 (0.04 V)] | [Status = "ERR_DISCONNECTED"] | [Exact] | [Lower open-circuit fault check] |
| **TV-04** | [Raw ADC count = 4050 (3.26 V)] | [Status = "ERR_SHORTED"] | [Exact] | [Upper short-circuit fault check] |
| **TV-05** | [4:1 Sand-Cement mix, 1/3 gal water] | [Holds shape when squeezed; no weep] | [Visual] | [Dry-pack deck mud consistency check] |

---

## 7. Assumptions & Open Technical Questions

*Document any technical assumptions, part tolerances, or unresolved questions that must be verified before final fabrication.*

- **Component Tolerances:** [e.g., Assumes divider resistor is 0.1% tolerance; if using 1% resistor, software calibration offset is required.]
- **Environmental Ratings:** [e.g., Assumes thermistor epoxy head is submersible; verify waterproof potting with test sample.]
- **Open Questions:** [e.g., Confirm whether 2-inch drain clamping ring bolts are 304 or 316 stainless steel for corrosion resistance.]
