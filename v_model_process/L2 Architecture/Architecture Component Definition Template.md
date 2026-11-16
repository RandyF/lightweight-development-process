# Architecture Component Definition Template

*Use this template at Level 2 (L2) of the lightweight V-Model when a project component has a complex sub-component tree, spans multiple trades or disciplines, or requires standalone revision tracking before detailed Level 3 decomposition. For simpler builds with fewer than 10 parts, keeping a single table inside the Architecture Definition is sufficient.*

---

# Architecture Component: [Component Name]

- **Document ID:** ACD-[XXX] (e.g., `ACD-001: Shower Drain Assembly` or `ACD-002: Outdoor Sensor Node`)
- **System Grouping:** [System Name, e.g., House Plumbing, Sensor Network, Electrical]
- **Parent Architecture:** [AD-XXX: Architecture Definition Name]
- **Physical Location:** [Specific physical location within the project footprint]
- **Lead Builder / Trade:** [Name or Specialty]
- **Status:** [Draft | In Review | Approved | Superseded]
- **Revision Date:** [YYYY-MM-DD]

---

## 1. Component Overview & Primary Function

*Summarize what this component does, its physical location, and its core job within the parent system architecture.*

- **Primary Function:** [One sentence describing the core job this component performs.]
- **Architectural Role:** [Explain how this component interacts with adjacent systems and supports the Level 1 project goals.]

---

## 2. System Context & Physical Envelope

*Describe where this component sits physically, its spatial boundaries, and its environmental exposure.*

- **Physical Envelope:** [Dimensions, clearances, and mounting space available.]
- **Environmental Exposure:** [Moisture, operating temperatures, dust, vibration, or weather conditions.]
- **Neighboring Systems:** [Surrounding structural elements, wiring chases, or piping runs.]

---

## 3. Sub-Component Hierarchy

*List the sub-components that make up this architecture component. Each sub-component represents a distinct assembly step or sub-part.*

| Sub-Component Name | Physical Location | Primary Function | Materials / Key Specifications |
| --- | --- | --- | --- |
| **[Sub-Component 1]** | [e.g., Below subfloor] | [e.g., Support drain body and establish pre-slope] | [e.g., Portland sand-cement mortar bed] |
| **[Sub-Component 2]** | [e.g., Clamped to drain flange] | [e.g., Watertight containment membrane] | [e.g., 40-mil flexible PVC sheet liner] |
| **[Sub-Component 3]** | [e.g., Drain center] | [e.g., Mechanical seal and pipe connection] | [e.g., 2-inch solvent-weld clamping drain body] |

---

## 4. Interfaces & Boundary Connections

*Define all connections where this component meets other components or external infrastructure. Specify exact dimensions, fittings, wire gauges, or protocols.*

| Interface ID | Interface Name | Direction / Type | Details, Ratings & Dimensions | Connects To (External or Sibling Component) |
| --- | --- | --- | --- | --- |
| **IF-01** | [e.g., Waste Drain Outlet] | Physical / Drainage | 2-inch Schedule 40 PVC solvent-weld | [House waste plumbing stack] |
| **IF-02** | [e.g., Liner Flange Clamp] | Mechanical | 304 Stainless steel machine bolts | [Clamping drain upper ring] |
| **IF-03** | [e.g., Perimeter Wall Overlap] | Physical Joint | Minimum 6-inch vertical turn-up | [Shower wall framing / backerboard] |

---

## 5. Codes, Standards & Critical Tolerances

*List non-negotiable building codes, manufacturer installation specifications, slope standards, or electrical ratings.*

- **Applicable Codes / Standards:** [e.g., Local plumbing code section on shower pan liners; UPC Section 412.0; NEC Article 210.]
- **Critical Tolerances:** [e.g., Minimum slope 1/4 inch per horizontal foot; flange bolts torqued evenly to 15 in-lbs.]
- **Inspection Checkpoints:** [e.g., Standing water flood test required before concealing behind mortar or wall board.]

---

## 6. Revision & Modification Log

*Track changes to this architecture component as the design evolves.*

| Revision | Date | Author | Summary of Changes |
| --- | --- | --- | --- |
| Rev 1.0 | [YYYY-MM-DD] | [Name] | Initial component specification created. |
| Rev 1.1 | [YYYY-MM-DD] | [Name] | [e.g., Updated drain flange specification based on code review.] |
