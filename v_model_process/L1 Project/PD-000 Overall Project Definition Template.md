# PD-000 Overall Project Definition Template

*Use this template to define an overarching master project at Level 1 (L1) of the lightweight V-Model. The PD-000 acts as an umbrella document for efforts that split into smaller, focused child projects. It coordinates two main project patterns: open-ended tool collections (such as an Onshape FeatureScript library) and large multi-phase builds (such as a bathroom remodel). Keep low-level engineering details in child project documents.*

---

# PD-000: [Master Project Name]

- **Document ID:** PD-000
- **Project Pattern:** [Open-Ended Tool Collection | Large Multi-Phase Project]
- **Lead Builder / Owner:** [Name]
- **Target Timeline:** [Start Date to Estimated Completion Date, or "Ongoing"]
- **Status:** [Active | In Planning | Completed | Archived]
- **Revision Date:** [YYYY-MM-DD]

---

## 1. Master Vision & Intent

*Describe the master purpose of this entire project. Explain why this effort needs an umbrella structure instead of isolated, one-off builds.*

- **Core Vision:** [What is the ultimate goal or "North Star" of this initiative?]
- **Why an Umbrella Approach:** [Why does this project need coordination across multiple sub-projects? e.g., shared room footprint, shared CAD repository, or sequential construction phases.]
- **Overall Long-Term Outcome:** [What does complete success look like for the overall endeavor?]

---

## 2. Global Scope & Boundary Envelope

*Define the boundaries for the entire initiative. Be explicit about what is included and what is strictly off-limits across all child projects.*

### Included in Overall Scope
- [Major system or capability 1]
- [Major system or capability 2]
- [Major system or capability 3]

### Strictly Out of Scope (Global Exclusions)
- [System, room, or capability deliberately excluded from this entire endeavor]
- [External integration or structural modification that is strictly off-limits]
- [Feature that belongs in an entirely separate future program]

---

## 3. Shared Operating Environment & Ecosystem

*Describe the physical space, digital tools, or software ecosystem shared by all child projects.*

- **Physical Space & Footprint:** [e.g., existing 8 ft × 10 ft bathroom footprint, dedicated electronics workbench, van chassis envelope.]
- **Digital / Software Ecosystem:** [e.g., Onshape public document / linked workspace, central git repository, shared Home Assistant server, common MQTT broker.]
- **Shared Utilities & Infrastructure:** [e.g., 15A dedicated electrical circuit, central water main shutoff, 2.4 GHz IoT Wi-Fi subnet.]

---

## 4. Global Constraints & Guardrails

*Establish the overarching rules, limits, and safety boundaries that every child project must obey.*

- **Overall Budget Ceiling:** [e.g., Total cost cannot exceed \$8,000 across all child projects.]
- **Safety & Regulatory Rules:** [e.g., All plumbing and electrical must satisfy local building codes; GFCI protection required on all bathroom circuits; mains power work requires main breaker shutoff.]
- **Operational Uptime Constraints:** [e.g., Water service to the rest of the house must be restored by 6:00 PM every day; household Wi-Fi must remain functional.]
- **Environmental Limits:** [e.g., Materials must withstand high humidity and direct water splash; operating temperature range from -10 °C to 45 °C.]

---

## 5. Sub-Project Roadmap & Work Breakdown

*Break the overall project into a sequence or catalog of focused child projects. Each child project runs its own V-cycle and creates its own Project Definition document (e.g., `PD-001`, `PD-002`).*

| Sub-Project ID | Title / Phase | Pattern / Scope Summary | Prerequisites / Dependencies | Target Status |
| --- | --- | --- | --- | --- |
| **PD-001** | [Sub-Project 1 Title] | [Brief summary of scope and main deliverable] | [None / Phase 1 start] | [Planned / Active / Complete] |
| **PD-002** | [Sub-Project 2 Title] | [Brief summary of scope and main deliverable] | [Requires PD-001 completion] | [Planned] |
| **PD-003** | [Sub-Project 3 Title] | [Brief summary of scope and main deliverable] | [Requires PD-002 completion] | [Planned] |
| **PD-004** | [Sub-Project 4 Title] | [Brief summary of scope and main deliverable] | [Requires PD-003 completion] | [Planned] |
| **PD-005** | [Sub-Project 5 Title] | [Brief summary of scope and main deliverable] | [Requires PD-004 completion] | [Planned] |

### Roadmap Guidelines
- **For Multi-Phase Builds:** [Define phase-gate criteria before advancing from one child project to the next, such as passing a rough-in water test before installing wallboard.]
- **For Open-Ended Collections:** [Define the quality bar for adding a new tool to the library, such as passing unit tests and including documentation.]

---

## 6. Shared Standards & Quality Conventions

*Define the common rules that keep all child projects consistent, compatible, and maintainable.*

- **Units of Measure & Tolerances:** [e.g., Metric default with internal millimeter units; imperial dimensions for structural framing; general tolerance ±0.5 mm.]
- **Naming Conventions:** [e.g., Script functions named `verbNoun`; CAD feature icon size 64×64 SVG; sub-project files named `PD-XXX-[Title]`.]
- **Hardware Standardization:** [e.g., Standardize on M3 socket-head screws; standardize on 18 AWG silicone wire; standardize on ESP32-C3 microcontrollers.]
- **Code & Repository Conventions:** [e.g., All code formatted using standard style; feature branches merged via pull request; Part Studios must include a test configuration.]

---

## 7. Master Goals Review & Program Validation

*Explain how you will verify that the overall project succeeds as a complete system.*

- **Multi-Phase Final Integration:** [e.g., Final building inspection passed; continuous 14-day operational use of all bathroom fixtures with zero leaks and reliable ventilation.]
- **Open-Ended Collection Health:** [e.g., All feature scripts generate valid CAD geometry without throwing errors in downstream assemblies; scripts are well-documented and easy to use.]
- **Overall Budget & Schedule Audit:** [Verify total actual expenses against the global budget ceiling; record lessons learned.]

---

## 8. Sub-Project Log & Revision History

*Track the addition and completion of child projects over the life of the master project.*

| Date | Sub-Project | Action / Update | Lead Builder |
| --- | --- | --- | --- |
| [YYYY-MM-DD] | PD-000 | Master project definition created. | [Name] |
| [YYYY-MM-DD] | PD-001 | [e.g., Phase 1 completed and verified.] | [Name] |
| [YYYY-MM-DD] | PD-002 | [e.g., Phase 2 kicked off.] | [Name] |

