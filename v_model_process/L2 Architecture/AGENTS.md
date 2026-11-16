# Agent Guidelines - Workspace Orientation: Level 2 (L2) Architecture

## Workspace Overview
This directory contains guidelines, reference documents, and templates for Level 2 (L2) of the lightweight V-Model. Level 2 defines system architecture, component decomposition, interfaces, constraints, and failure modes on the left side of the V, and verifies their integrated operation through System Testing on the bench on the right side of the V.

## Core Rules & Invariants
- **Reference Ruleset Only:** These documents define the rules, structures, and templates for managing external projects. Do not record project-specific architecture directly inside these reference files.
- **System Decomposition & Seams:** Level 2 addresses **where** functions live, how responsibilities are partitioned, and how subsystems communicate. It does not define how each component works internally (that occurs at Level 3).
- **Impact Matrix Requirement:** Every Architecture Definition must include an Impact Matrix cataloging every touched system as New, Modified, or Unchanged.
- **Identification & Traceability Discipline:**
  - System Interactions: `INT-n` (e.g., `INT-1: Sensor Node publishes telemetry via MQTT`)
  - Failure Modes: `FM-n` (e.g., `FM-1: Wi-Fi disconnect triggers low-power fallback`)
  - Non-Functional Requirements: `NFR-n` (e.g., `NFR-1: Wake-to-publish latency under 2.5 seconds`)
  - System Test Cases: `ST-nnn` (e.g., `ST-001: Telemetry timing and payload verification`)
- **System Test Planning:** Author the System Test Plan during the architecture design phase before implementation begins. Every interaction (`INT-n`), failure mode (`FM-n`), and non-functional requirement (`NFR-n`) must have at least one test case on prototype bench hardware.
- **Component Inventory:** Use the Architecture Components guidelines to catalogue parts, locations, and interfaces before writing individual Level 3 Component Definitions.

## Architecture Map & Context Index
- `Architecture Definition & System Testing.md` -> Comprehensive guide covering system boundaries, impact matrix, interface contracts, constraints, failure modes, and system integration testing.
- `Architecture Definition Template.md` -> Standard template for system architecture definitions (`AD-xxx`).
- `Architecture Components.md` -> Guide and structuring pattern for compiling the project-wide inventory of systems, components, locations, and interfaces.
- `Architecture Component Definition Template.md` -> Dedicated template for documenting complex architecture components with nested sub-components, cross-trade boundaries, and standalone revision tracking.
