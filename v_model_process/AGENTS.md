# Agent Guidelines - Workspace Orientation: V-Model Process

## Workspace Overview
This directory contains reference documentation, templates, and process guidelines for executing hobby, DIY, maker, and small-scale engineering projects. The framework adapts the systems engineering V-Model into a lightweight, practical lifecycle designed to minimize rework, eliminate unverified assumptions, and enforce clear verification and validation contracts.

## Core Rules & Invariants
- **Reference-Only Documentation:** The documents in this directory define the rules, structures, and templates for managing external projects. Do not treat these files as project-specific project deliverables.
- **Context Isolation:** When building agent task context, traverse only into the directories relevant to the current lifecycle level. For example, when authoring an L3 Component Definition, do not ingest L4/L5 files unless explicitly requested.
- **Tone and Reading Level:** Write all documentation to a 10th-grade reading level using an instructional, declarative tone. Eliminate conversational fillers, informal idioms, and vague generalities.
- **Traceability Discipline:** Every requirement, interface, failure mode, and test case must use its standardized prefix ID:
  - **L1 Project:** `PD-000` (Master Project), `PD-xxx` (Project Definition), `AC-n` (Acceptance Criteria), `PGR` (Project Goals Review / Validation)
  - **L2 Architecture:** `AD-xxx` (Architecture Definition), `INT-n` (Interactions / Data Flows), `FM-n` (Failure Modes), `NFR-n` (Non-Functional Requirements), `ST-nnn` (System Tests)
  - **L3 Component:** `CD-xxx` (Component Definition), `RESP-n` (Responsibilities), `IF-nn` (Interfaces), `CT-nnn` (Component Tests)
  - **L4/L5 Functional & Technical Implementation:** `FD-xxx` (Functional Definition), `FD-xxx-n.n` (Functional Statements), `TD-xxx` (Technical Definition), `TV-nn` (Test Vectors), `BM-nn` (Inspection Benchmarks), `UT-nnn` (Unit Tests), `IMP` (Implementation Records)
- **Standard Formatting** Use Markdown for all requirements formatting unless otherwise specified.
- **Visual Models:** Use Mermaid diagrams (`flowchart`, `sequenceDiagram`, `stateDiagram-v2`) to illustrate system boundaries, sequencing, and decomposition.
- **Grounded Content:** Avoid assumptions, unverified claims, or undocumented external services. Couch necessary design assumptions with `[suggested]`.
- **Directory Maintenance:** Keep directory-level `AGENTS.md` files updated whenever adding, renaming, or re-scoping files.

## Architecture Map & Context Index
- `V-Cycle for Lightweight Development.md` -> Master lifecycle overview, level decomposition, tailoring matrix, and traceability principles.
- `/L1 Project` -> Top-level project definition, scope boundaries, user acceptance criteria, and operational validation (Project Goals Review).
- `/L2 Architecture` -> System decomposition, subsystem boundaries, data flows, interface definitions, failure modes, and system integration testing.
- `/L3 Component` -> Isolated component, module, or trade definitions, physical interfaces, material specifications, and component proof testing.
- `/L4L5 Function Technical Implementation` -> Low-level functional logic, exact technical specifications, fabrication/coding implementation guidelines, and unit testing.
