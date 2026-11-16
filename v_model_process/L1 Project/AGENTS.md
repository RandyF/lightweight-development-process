# Agent Guidelines - Workspace Orientation: Level 1 (L1) Project

## Workspace Overview
This directory contains guidelines, reference documents, and templates for Level 1 (L1) of the lightweight V-Model. Level 1 defines the project's purpose, operating setting, user scenarios, and acceptance criteria on the left side of the V, and validates the complete build in its real operating environment through the Project Goals Review (First Run) on the right side of the V.

## Core Rules & Invariants
- **Reference Ruleset Only:** These files define standards and templates for external projects. Do not author project-specific content directly inside these reference files.
- **Validation vs. Verification:** Level 1 is the only level focused on **validation** ("Did we build the right thing?"). It assesses whether the finished build solves the user's problem in real-world operation. Verification of technical specifications occurs at Levels 2 through 4.
- **Pattern Selection:**
  - Use `PD-000` (Overall Project Definition) when managing multi-phase builds (such as a room remodel) or open-ended tool collections (such as a CAD feature library).
  - Use standard `PD-xxx` (Project Definition, e.g., `PD-001`) for standalone builds that complete within a single continuous V-cycle.
- **Strict Abstraction Barrier:** Do not include component model numbers, GPIO pinouts, communication schemas, or algorithm logic in Level 1 requirements. Record early engineering ideas strictly in the "Early Technical Notes" scratchpad.
- **Observable Acceptance Criteria:** All acceptance criteria (`AC-n`) must be measurable and observable in daily operation without specialized laboratory equipment.
- **Predefined Validation Duration:** The operational test duration and pass/fail benchmarks must be defined in the Project Definition before construction begins.

## Architecture Map & Context Index
- `Project Definition & Project Goals Review.md` -> Comprehensive guide covering L1 Project Definition authoring, acceptance criteria formulation, and Project Goals Review execution.
- `Project Definition Template.md` -> Standard template for single-cycle projects and child sub-projects (`PD-xxx`).
- `PD-000 Overall Project Definition.md` -> Conceptual guide detailing master project patterns, child project roadmaps, and global boundary envelopes.
- `PD-000 Overall Project Definition Template.md` -> Master template for overarching programs coordinating multiple child sub-projects (`PD-000`).
