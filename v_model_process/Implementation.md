# Implementation

## At a Glance

| Aspect | Details |
| --- | --- |
| **Level** | L4 (Functionally) / L2–L3 (Architecturally) |
| **When You'll Use This** | When writing code, soldering wires, cutting materials, or assembling subassemblies that connect to higher-level definitions |
| **Document Pair** | Links to your Component Definition and Functional/Technical Definition at the same level |

Implementation is where you physically build what's been defined. It connects the design layers above (Architecture, Components) to the test verification below.

---

## Why Implementation Matters

Without implementation documentation:
- You don't know *exactly* what will be built
- Test failures give no clues about what to fix
- Reproducibility fails if someone else tries to repeat the work

Implementation documents create a concrete link between your tests and your real-world build. When a System Test passes, you now know which wires were soldered and which code was compiled.

---

## At-a-Glance Overview

The process flow:

```
    Architecture Def (L2)     Component Def (L3)
         ↓                             ↓
        System Testing (L2)      Component Testing (L3)
                           ↓              ↓
                       Functional Def (L4)
                               ↓
                            Implementation
                               ↓
                          Unit Testing (L4)
```

---

## Part 1: Functional Implementation

### When You Need This

Document your **code**, **logic**, or **functional procedures**. This applies to:
- Functions, methods, routines, algorithms
- Code compilation and linking steps
- Data transformations and calculations
- Sensor calibrations or signal processing

**Skip this section** if you're doing physical assembly, wiring, or material fabrication (use Physical Implementation below instead).

---

### Functional Implementation Checklist

| Check | Question |
| --- | --- |
| **Code location** | Where is the function defined? Which file and line number? |
| **Dependencies** | What headers, libraries, or data does it need? |
| **Inputs & Outputs** | What data goes in, what comes out (with types)? |
| **Behavior** | How does it handle normal and abnormal conditions? |
| **Testing link** | Which Unit Test verifies this function? |

---

## Part 2: Physical Implementation

### When You Need This

Document your **hardware**, **assembly**, or **material fabrication**. This applies to:
- Wire routing, PCB assembly, component placement
- Circuit wiring and connector connections
- Material cutting, sanding, assembling physical parts
- Fixture construction, test jig building

---

### Physical Implementation Checklist

| Check | Question |
| --- | --- |
| **Parts list** | What components and materials are needed? |
| **Assembly sequence** | In what order do you build it? |
| **Physical measurements** | Key dimensions, wire gauge, connector types |
| **Calibration setup** | Test fixtures, sensors, measurement equipment |
| **Testing link** | Which Component or System Test verifies this? |

---

## Common Pitfalls

| Pitfall | Problem | Solution |
| --- | --- | --- |
| **Vague descriptions** | "Wire connects sensor to MCU" doesn't say *how* | Specify exact wire gauge, routing path, and connector type |
| **No test link** | You don't know which test covers this implementation | Always cite the specific Unit or Component Test ID |
| **Missing dependencies** | Build fails because a library wasn't linked | Document all headers, libraries, and linker flags |
| **Assuming repeatability** | One person can build it, but not others | Make notes explicit—no "you get my drift" |

---

## Traceability

- **Parent:** Component Definition (`CD-XXX`) or Functional/Technical Definition (`FD-XXX` / `TD-XXX`)
- **Children:** Unit Test cases (`UT-XXX-nnn`), integration test setups, or physical inspection notes
- **Verified by:** Level 4 Unit Tests (`UT-XXX-nnn`) that directly reference the implementation details
