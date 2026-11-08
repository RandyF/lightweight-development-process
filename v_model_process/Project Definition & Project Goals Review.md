# Project Definition & Project Goals Review

## Project Definition

### Purpose

The Project Definition describes a feature or change **in terms of the Project and the people who use it**. It establishes the need, the expected outcome, and how we will know it succeeded. Every lower-level document traces back to it, so it must be clear enough to settle arguments later (“Is this in scope?”).

## At a Glance

|  | Project Definition (left side) | Project Goals Review (right side) |
| --- | --- | --- |
| **Question answered** | What does the Project need to do, and why? | Does it actually do that for real users on real machines? |
| **Perspective** | The customer’s view of the Project as a whole | The customer’s view of the Project as a whole |
| **Customers** | Internal: Operations, Maintenance, and other teams who run or service the units | Same |
| **Written / run by** | Project owner or engineering lead, with Operations and Maintenance | Engineering, with Operations and Maintenance running the units |
| **Environment** | — | Operational Project Goals Review units |

---

### What Belongs Here

| Section | Guidance |
| --- | --- |
| **Problem Statement** | What problem exists today, and who has it? Write it from the customer’s point of view. |
| **Stakeholders & Users** | Who uses the feature, who is affected by it, who must approve it. |
| **User Scenarios** | Short narratives or user stories: “As a maintenance technician, I need to… so that…”. Include abnormal scenarios (power loss, a fault during a process cycle), not just the happy path. |
| **Acceptance Criteria** | Measurable, observable outcomes at the Project boundary. This is the section Project Goals Review verifies directly. |
| **Operational Impact** | Changes to procedures, training, maintenance schedules, or dashboards. Include any downtime needed to deploy. |
| **Safety & Compliance Considerations** | Any effect on how the unit protects people, the process, or equipment. Flag these early; they tighten every level below. |
| **Scope / Out of Scope** | Be explicit about what this effort will *not* do. |
| **Project Goals Review Plan** | Which units, how many, for how long, and who signs off (see Project Goals Review below). |
| **Dependencies** | Other Projects, teams, backend or supervisory software changes, hardware availability. |

### What Does Not Belong Here

- Which processor, PCBA, or firmware module does the work (that is L2/L3)
- MQTT topics, CAN message IDs, JSON field names (that is L2/L4)
- Algorithms, thresholds, or state machines (that is L4)
    
    If you catch yourself writing these, note them in an “Early Technical Notes” appendix for the architecture author and keep going.
    

---

### Writing Good Acceptance Criteria

Acceptance criteria must be **observable by the customer** without special tools, and **measurable** enough that two people would agree on pass or fail.

| Weak | Strong |
| --- | --- |
| “Faults should be reported quickly.” | “A detected fault appears on the Operations dashboard within 10 seconds of detection.” |
| “The system should be reliable.” | “Over a 14-day Project Goals Review soak across 3 units, no unplanned controller reboots occur.” |
| “Maintenance can see what’s wrong.” | “For every active fault, the dashboard shows the faulted component, whether it is an error or a warning, the occurrence count, and when it first occurred.” |
| “Must not disrupt operations.” | “Deploying the update requires no more than 15 minutes of downtime per unit and does not interrupt an active process cycle.” |

### Example (Illustrative)

> **Project Definition: Home Temperature Monitoring**
> 
> 
> **Problem:** We want to use a comprehensiove set of temperature sensors around the house and be able to use those in HomeKit
> 
> **Scenario:** Is it time to turn on the house fans?
> 
> **Acceptance criteria:**
> 
> 1. temperaturte sensors are available in homekit
> 
> **Project Goals Review:** Homekit displays and reacts to temperatures
> 

---

## Project Goals Review

### Purpose

Project Goals Review **validates** the change: it confirms that the feature solves the real problem, on real Project Goals Review units, under real operating conditions, for a **prescribed amount of time**. It is the only level where real users, real process loads, and real environmental variation all appear at once.

Project Goals Review is **not** where we find integration bugs. Those should have been caught in System Testing. Finding one here means a lower level had a gap, and that gap gets fixed as well.

### Environment

- Operational Project Goals Review units, running normal processes
- Operated by Operations staff, not engineers
- Monitored through standard telemetry plus any feature-specific monitoring defined in the Project Definition

### Entry Criteria

- [ ]  System Testing (L2) passed and signed off
- [ ]  Monitoring in place for the acceptance criteria and for general health
- [ ]  Release notes written for Operations and Maintenance
- [ ]  **Rollback plan** documented and rehearsed: how to return each unit to the previous firmware, how long it takes, and who can do it
    - [ ]  Operations has agreed on which units, and when

### Exit Criteria

Record a **baseline** from the same units before the update, so “is this normal?” has an answer.

- [ ]  All acceptance criteria met for the full soak duration on all pilot units
- [ ]  No regression in general health signals versus baseline
- [ ]  No open defects rated above the agreed severity
- [ ]  Operations and Maintenance sign-off recorded on the Project Definition

### What to Monitor

**Feature-specific:** Each acceptance criterion in the Project Definition, measured continuously where possible rather than spot-checked.

**General health, on every Project Goals Review test:**

| Signal | Why it matters |
| --- | --- |
| Reboot count and reset reason, per processor | Unexpected resets are often the first sign of crashes, watchdog timeouts, or brown-outs. |
| Uptime per processor | Confirms reboots are not being missed between samples. |
| Free heap per processor | A steady decline means a leak. Sawtooth patterns can indicate fragmentation. |
| Heartbeat / connectivity | Detects network or MQTT stack issues. |
| Fault and warning rates | Compare against the unit’s baseline before the update. A rise is a regression even if unrelated to the feature. |
| Process outcomes | The Project’s actual job, which must be no worse than before. |

### Soak Duration: How Long Is “Long Enough”?

The Project Definition sets the duration. Choose it based on:

- **Process cycle length.** The soak should cover several complete process cycles, not just a slice of one.
- **Rare events.** If the feature responds to something that happens weekly, a three-day soak proves nothing.
- **Slow failures.** Memory leaks, heap fragmentation, sensor drift, and counter overflows can take days to show up.
- **Risk.** Changes that touch control loops or safety behavior warrant longer soaks and more units.

### Traceability

- **Parent:** None (L1 is the top), though it may reference a roadmap item or business objective.
- **Children:** One or more Architecture Definitions.
- **Verified by:** The Project Goals Review Test Plan and its records.

---

## Common Pitfalls

| Pitfall | Fix |
| --- | --- |
| Acceptance criteria describe implementation (“Publish on topic X”) | Rewrite in terms of what the customer sees. |
| No soak duration specified, so testing ends when people get bored | Set the duration in the Project Definition, before implementation starts. |
| Operations and Maintenance first see the feature at deployment | Involve them when writing the Project Definition. They are the customer. |
| No baseline data, so “is this worse?” cannot be answered | Capture baseline health metrics before deployment. |
| Rollback plan exists but has never been tried | Rehearse it on a non-Project Goals Review unit during System Testing. |

### Example Test Record (Illustrative)

| Field | Value |
| --- | --- |
| Verifies | Project Definition: Remote Fault Visibility, criteria 1 to 4 |
| Units | Vessel 12 (days 1 to 7); Vessels 12, 15, 21 (days 8 to 21) |
| Firmware | Processor-A x.y.z, Processor-B x.y.z, Secondary x.y.z |
| Result | Criterion 1: 47 faults observed, max latency 4.2 s. Pass.  Criterion 4: 0 false dispatches. Pass. |
| Health | 0 unplanned reboots; free heap stable within ±2% |
| Sign-off | Maintenance lead, Operations lead, dates. |