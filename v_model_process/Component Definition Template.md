# Component Definition Template

*Use this template to define a single component, physical assembly, or trade at Level 3 (L3) of the lightweight V-Model. The Component Definition describes how one part of your build carries out its assigned job from the parent Architecture Definition. It sets responsibilities, physical interfaces, material rules, and installation standards in isolation before final assembly.*

---

# [Component Name]

- **Document ID:** CD-[XXX] (e.g., `CD-004: Shower Waterproofing Pan` or `CD-002: Sensor Node`)
- **Parent Architecture:** [AD-XXX: Architecture Definition Name]
- **Parent Project:** [PD-XXX: Project Definition Name]
- **Component Domain:** [Physical Trade / Mechanical Assembly / Electrical Circuit / Software Module]
- **Author / Builder:** [Name]
- **Status:** [Draft | In Review | In Rough-in / Fabrication | In Component Testing | Complete]
- **Target Date:** [YYYY-MM-DD]

---

## 1. Component Overview & Scope

*Provide a brief summary of this component. Explain what it is, why it exists as a separate piece, and which part of the system architecture it fulfills.*

- **Component Purpose:** [Summarize what this component does in 1–2 sentences.]
- **Role in the Architecture:** [Explain how this component connects to surrounding parts or trades in the parent architecture.]

---

## 2. Physical Location & Boundaries

*Specify where this component lives physically and where its boundaries begin and end.*

- **Physical Location / Zone:** [e.g., Master bathroom shower floor area (36 in x 48 in footprint), North patio exterior wall, workshop bench frame.]
- **Component Boundaries:** [Define what belongs to this component versus adjacent components. e.g., "Includes shower pan liner and clamping drain; does not include vertical backerboard or wall tile."]

---

## 3. Component Responsibilities & Performance Criteria

*List the specific functions, structural standards, or performance criteria this component owns. Each numbered responsibility will decompose into one or more child Functional Definitions (Level 4).*

1. **[RESP-1]:** [Primary function, e.g., Form a 100% watertight basin to contain daily shower water.]
2. **[RESP-2]:** [Slope / dimensional criteria, e.g., Maintain a continuous pre-slope of at least 1/4 inch per foot toward the central drain.]
3. **[RESP-3]:** [Boundary overlap, e.g., Extend waterproof barrier at least 6 inches up all surrounding wall studs and over the curb.]
4. **[RESP-4]:** [Structural / load criteria, e.g., Provide a sound, deflection-free bonding surface for floor tile.]
5. **[RESP-5]:** [Durability / safety, e.g., Withstand normal foot traffic without puncturing or tearing the membrane.]

---

## 4. Interfaces & Connections

*List every physical joint, pipe fitting, electrical terminal, or communication line crossing this component boundary. Always specify dimensions, thread types, and ratings.*

| Interface ID | Interface Name | Connection Type | Dimensions / Ratings / Units | Connects To |
| --- | --- | --- | --- | --- |
| **IF-01** | `[e.g., Central Drain Connection]` | Mechanical clamping flange | 2-inch Schedule 40 PVC | [Household waste stack] |
| **IF-02** | `[e.g., Wall Stud Overlap]` | Physical overlap joint | >= 6 inches vertical overlap | [Cement backerboard] |
| **IF-03** | `[e.g., Shower Curb Interface]` | Membrane wrap | Fully wrapped over curb core | [Bathroom subfloor] |
| **IF-04** | `[e.g., Electrical Feed (if applicable)]` | Hardwired terminal | 12/2 NM-B Romex, 20A 120V | [Branch circuit junction box] |

---

## 5. Materials, Parts & Specifications

*Identify all required lumber grades, pipe schedules, wire gauges, or component breakout boards.*

- **Core Structural Materials:** [e.g., 40-mil PVC pan liner, pre-slope sand-and-cement mortar bed, 2x4 framing lumber.]
- **Fittings & Hardware:** [e.g., 2-inch PVC clamping shower drain with stainless steel bolts, silicone sealant.]
- **Required Tools for Assembly:** [e.g., Level, margin trowel, PVC solvent weld and primer, mechanical test plug.]

---

## 6. Installation Rules, Tolerances & Critical Constraints

*Document non-negotiable building codes, slope rules, fastener spacing, torque specs, or cure times.*

- **Slope & Alignment Rules:** [e.g., Pre-slope must be minimum 1/4 inch per foot from perimeter to drain; pan must be level along curb top.]
- **Fastening & Penetration Rules:** [e.g., No nails or screws through the pan liner below 3 inches above the curb top.]
- **Cure Times & Environmental Limits:** [e.g., Allow mortar bed to cure for 24 hours before performing flood test.]

---

## 7. Safety & Hazard Precautions

*List safety precautions specific to this module during fabrication, assembly, and testing.*

- [ ] **Water & Pressure Hazards:** [e.g., Verify main water shutoff valve is operable before testing plumbing.]
- [ ] **Chemical & Fume Safety:** [e.g., Provide open-window ventilation when applying PVC solvent primer and silicone.]
- [ ] **Electrical Isolation:** [e.g., Confirm breaker is locked out before working near electrical junction boxes.]
- [ ] **PPE Requirements:** [e.g., Wear safety glasses, dust mask during mortar mixing, and work gloves.]

---

## 8. Component Lifecycle & Build Stages

*Identify the build stages for this component. For physical builds, show progress from rough-in to finish.*

- **`ROUGH-IN`**: [Initial framing, pre-slope mortar bed placed, drain flange mounted.]
- **`INSPECTION & TEST`**: [Drain plugged, 24-hour standing water flood test performed.]
- **`ENCLOSED`**: [Final mortar bed poured, backerboard installed over liner apron.]
- **`FINISHED`**: [Tile set, grouted, and silicone expansion joints caulked.]

---

## 9. Component Test Plan (Right Side of the V)

*Outline how this component will be tested in isolation before connecting to the full project or closing walls. Every responsibility must be verified.*

### Test Setup & Equipment
- **Test Equipment:** [e.g., Mechanical 2-inch rubber test plug, clean water supply, measuring tape, moisture meter.]
- **Test Location:** [Shower pan rough-in area before hanging wall backerboard.]

### Entry Criteria
- [ ] Pan liner and clamping drain installed per manufacturer instructions.
- [ ] Corner dams folded and sealed with approved adhesive.
- [ ] Drain test plug inserted and expanded tightly.

### Exit Criteria
- [ ] Zero drop in water level over 24 hours (excluding minor evaporation under 1/16 inch).
- [ ] Zero moisture detected on subfloor or framing below the shower.
- [ ] Test signed off and photographed before any mortar or tile is installed.

### Component Test Cases

| Test ID | Verifies (RESP / IF) | Test Procedure Summary | Expected Result | Pass / Fail |
| --- | --- | --- | --- | --- |
| **CT-001** | [RESP-1, IF-01] | [Insert test plug into drain. Fill pan with water to 1/2 in below curb top. Mark line with tape. Wait 24 h.] | [Water level holds with zero drop; framing below stays 100% dry.] | [ ] |
| **CT-002** | [RESP-2] | [Check slope from corners to drain using a digital torpedo level.] | [Slope reads >= 1/4 inch per foot across all quadrants.] | [ ] |
| **CT-003** | [RESP-3, IF-02] | [Measure height of membrane above curb top around all three walls.] | [Membrane height is >= 6 inches above curb line.] | [ ] |

---

## 10. Early Technical Notes (Scratchpad for Level 4)

*Do not put detailed cut lists, individual screw counts, or minute tile layouts in the component sections above. Record early technical details here for the Level 4 phase.*

- *Cut Dimensions:* [e.g., Pan liner cut size 5 ft x 6 ft to allow 10-inch turn-ups on all sides.]
- *Mortar Ratios:* [e.g., 4 parts sand to 1 part Portland cement mixed to damp sand consistency.]
- *Detailed Fastener Specs:* [e.g., 1-1/4 inch hot-dipped galvanized roofing nails along top edge only.]
