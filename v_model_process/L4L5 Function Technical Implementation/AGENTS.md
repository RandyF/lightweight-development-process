# Agent Guidelines - Workspace Orientation: Level 4 / Level 5 (L4/L5) Function, Technical & Implementation

## Workspace Overview
This directory contains guidelines, reference documents, and templates for Level 4 (L4) and Level 5 (L5) of the lightweight V-Model. Level 4 defines detailed function and mechanism behavior (Functional Definition), exact specifications, pinouts, and constants (Technical Definition), and verifies them through Unit Testing. Level 5 defines Implementation—the physical fabrication, circuit wiring, and source code development that takes place at the base of the V.

## Core Rules & Invariants
- **Reference Ruleset Only:** These documents define the rules, structures, and templates for managing external projects. Do not author project-specific functional, technical, or implementation files directly inside these reference files.
- **Separation of Behavior and Parameters:** Keep behavioral logic (how an operation or mechanism functions under normal and edge conditions) in the Functional Definition (`FD-xxx`). Keep exact numerical constants, formulas, pin maps, and payload schemas in the Technical Definition (`TD-xxx`). This ensures changing a calibration number or material mix does not require rewriting behavioral logic.
- **Identification & Traceability Discipline:**
  - Functional Definitions: `FD-xxx` (e.g., `FD-DRAIN-01: Shower Drain Pre-Slope Pitch`)
  - Functional Statements: `FD-xxx-n.n` (e.g., `FD-TEMP-01.1: Capture 5 consecutive samples at 50 ms intervals`)
  - Technical Definitions: `TD-xxx` (e.g., `TD-TEMP-01: Steinhart-Hart Constants & ADC Map`)
  - Test Vectors: `TV-nn` / `TV-xxx-nn` (executable test data pairs with known inputs and expected outputs)
  - Inspection Benchmarks: `BM-nn` / `BM-xxx-nn` (physical measurement checkpoints, e.g., level pitch or mortar slump)
  - Unit Test Cases: `UT-nnn` (isolated checks verifying specific `FD-xxx-n.n` statements or `TV` vectors)
  - Implementation Records: `IMP-xxx-nn` (concrete execution logs, commit hashes, or build notes)
- **Design for Testability:** Structure algorithms and calculations so they take inputs as parameters and return values without direct hardware side effects. This allows testing routines on a developer workstation before flashing microcontrollers. In physical trades, perform dimensional inspections and dry test-fits before applying glue, solvent, or mortar.
- **Mandatory Shall Statements:** Every functional requirement must use numbered "shall" statements that specify observable, testable behavior.

## Architecture Map & Context Index
- `Functional & Technical Definition & Unit Testing.md` -> Comprehensive guide covering behavioral decomposition, technical specification authoring, test vector creation, and unit test execution.
- `Functional Definition Template.md` -> Standard template for detailing function, mechanism, or routine behavior (`FD-xxx`).
- `Technical Definition Template.md` -> Standard template for exact numerical formulas, pinout tables, data schemas, and test vectors (`TD-xxx`).
- `Implementation.md` -> Master lifecycle guide for physical fabrication, circuit assembly, software coding, dependency pinning, and execution records (`IMP`).
