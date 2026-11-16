# Agent Guidelines - Workspace Orientation: Level 3 (L3) Component

## Workspace Overview
This directory contains guidelines, reference documents, and templates for Level 3 (L3) of the lightweight V-Model. Level 3 defines the scope, physical boundaries, responsibilities, interfaces, and material requirements of individual components, physical assemblies, or trades on the left side of the V, and verifies them through isolated Component Testing on the right side of the V before system-level assembly.

## Core Rules & Invariants
- **Reference Ruleset Only:** These documents define the rules, structures, and templates for managing external projects. Do not author project-specific component records directly inside these reference files.
- **The Golden Rule of Level 3:** Never conceal or bury an unverified component behind drywall, mortar, glue, paint, or sealed enclosures. Proof-test every component in isolation while repair access remains open.
- **Component Isolation:** Treat each component, physical assembly, or trade as a self-contained unit with clear physical boundaries. Avoid broad whole-system architecture (Level 2) and line-by-line cut dimensions, pin registers, or calculation algorithms (Level 4).
- **Identification & Traceability Discipline:**
  - Component Definitions: `CD-xxx` (e.g., `CD-001: Outdoor Sensor Probe Assembly` or `CD-004: Shower Waterproofing Pan`)
  - Responsibilities: `RESP-n` (e.g., `RESP-1: Form a 100% watertight containment basin`)
  - Physical & Data Interfaces: `IF-nn` (e.g., `IF-01: Central drain clamping flange to waste stack`)
  - Component Test Cases: `CT-nnn` (e.g., `CT-001: 24-hour standing water flood test`)
- **Lifecycle & Build Stages:** Track physical assemblies through defined lifecycle stages: `ROUGH-IN` -> `INSPECTION & TEST` -> `ENCLOSED` -> `FINISHED` (or operational modes for electronics: `BOOT`, `SAMPLE`, `TRANSMIT`, `SLEEP`, `FAULT`).
- **Comprehensive Proof Testing:** Select appropriate component verification methods: standing water flood tests, pneumatic/hydraulic pressure holds, electrical continuity checks, dimensional/squareness inspections, and dry-fit verifications.

## Architecture Map & Context Index
- `Component Definition & Component Testing.md` -> Comprehensive guide covering component scoping, physical interfaces, material grades, installation tolerances, and isolated proof testing.
- `Component Definition Template.md` -> Standard template for authoring component definitions (`CD-xxx`).
