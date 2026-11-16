# Project Definition Template

*Use this template to define a single project or sub-project at Level 1 (L1) of the lightweight V-Model. It establishes user needs, operating context, and measurable acceptance criteria before technical design begins. Keep low-level technical choices (pinouts, chip models, code schemas) in the Early Technical Notes scratchpad at the end.*

---

# [Project Title]

- **Document ID:** PD-[XXX] (e.g., `PD-001` or `PRJ-TEMP`)
- **Parent Project:** [PD-000: Overall Project Name | None (Standalone Project)]
- **Author / Builder:** [Name]
- **Status:** [Draft | In Review | In Progress | In Validation | Complete]
- **Target Date:** [YYYY-MM-DD]

---

## 1. Problem Statement

*Describe the problem from the user perspective. Explain who experiences the issue, what happens today, and why solving it matters. Avoid specifying technical solutions here.*

- **Current Situation:** [Describe what is happening right now.]
- **The Problem:** [Explain why the current situation is frustrating, inefficient, or broken.]
- **Desired Outcome:** [Describe what success looks like for the user once this build is finished.]

---

## 2. Target Users & Operating Context

*Identify who will interact with the completed build and where it will operate.*

- **Primary Users:** [The builder, household members, workshop collaborators, or hobby community.]
- **Operating Setting:** [Where will this live? e.g., outdoors on a north patio, mounted in a hallway, in a garage workshop.]
- **Environmental Factors:** [Temperature swings, direct sunlight, moisture, dust, vibration, or physical access limits.]

---

## 3. User Scenarios

*Write short descriptions showing how the build works in everyday life. Include normal workflows, edge cases, and failure modes.*

### Scenario A: Normal Daily Use
- *As a [user type], I want to [perform an action] so that [benefit achieved].*

### Scenario B: Event-Driven or Infrequent Use
- *When [specific event occurs, such as outdoor temperature dropping below indoor temperature], the system should [action or notification].*

### Scenario C: Failure Handling & Recovery
- *If [power fails, Wi-Fi disconnects, or a sensor freezes], the system should [safe fallback behavior, such as showing an offline status indicator instead of stale data].*

---

## 4. Acceptance Criteria

*List measurable, observable criteria that prove the build succeeded. These criteria are verified directly during the Project Goals Review (First Run). Criteria must be observable in daily use without specialized laboratory equipment.*

| ID | Acceptance Criterion | Verification Method |
| --- | --- | --- |
| **AC-1** | [Observable behavior, e.g., "Readings update on dashboard within 10 seconds of change."] | [Daily observation / dashboard check] |
| **AC-2** | [Accuracy or performance limit, e.g., "Accurate within ±0.5 °C against reference."] | [Comparison check against reference] |
| **AC-3** | [Reliability metric, e.g., "Runs continuously for 14 days without crashing or rebooting."] | [Uptime and reset log check] |
| **AC-4** | [Battery or power goal, e.g., "Runs for at least 6 months on a single 18650 cell."] | [14-day voltage drop projection] |
| **AC-5** | [Failure response, e.g., "Marks sensor offline within 5 minutes of power loss."] | [Simulated power disconnect test] |

---

## 5. Physical Setup & Environmental Requirements

*Detail the physical and practical requirements for installing, running, and maintaining the build.*

- **Mounting & Housing:** [Enclosure type, 3D printed case, wall mount, DIN rail, weather shielding.]
- **Power Source:** [Battery type, 5V USB-C, 12V DC adapter, solar panel, wall outlet.]
- **Weatherproofing & Thermal Needs:** [IP rating, operating temperature range, airflow or heatsinking.]
- **Routine Maintenance:** [Battery swap interval, sensor cleaning, filter replacement, physical access needs.]

---

## 6. Safety & Hazard Considerations

*Identify potential hazards early to plan safe enclosures, proper fusing, and reliable isolation.*

- [ ] **Mains Voltage (120V/240V):** [Proper enclosure, terminal barriers, grounding, fuse protection.]
- [ ] **High Current / Wiring:** [Correct wire gauge, inline fusing, secure crimps.]
- [ ] **Lithium Batteries:** [BMS protection board, charging cutoff, thermal isolation.]
- [ ] **Heat & Fire Hazards:** [Adequate heatsinking, flame-retardant materials, clearance from flammables.]
- [ ] **Moving Parts:** [Pinch point guards, emergency stop, stall detection.]
- [ ] **Water & Moisture:** [Drip loops, silicone seals, conformal coating.]

---

## 7. Scope & Boundaries

*Be explicit about what this specific project will and will not do to prevent scope creep.*

### In Scope
- [Must-have capability 1]
- [Must-have capability 2]
- [Must-have capability 3]

### Out of Scope
- [Feature deferred to a future project]
- [Feature deliberately excluded]
- [Integration deliberately avoided]

---

## 8. Validation Plan (Project Goals Review / First Run)

*Outline how you will validate the completed build in its real environment before declaring victory.*

- **Test Setting:** [Installed in actual deployment location under real daily conditions.]
- **Evaluation Duration:** [e.g., 14 continuous days covering day/night cycles.]
- **Baseline Metrics to Capture:** [Idle current draw, initial Wi-Fi signal, starting battery voltage.]
- **Pass / Fail Conditions:** [All acceptance criteria (AC-1 through AC-5) pass with zero unplanned reboots.]
- **Rollback / Recovery Plan:** [Known-good backup firmware, configuration backup, spare hardware ready if testing fails.]

---

## 9. External Dependencies

*List external systems, parts, and platforms needed for project success.*

- **Networks & Protocols:** [Home 2.4 GHz Wi-Fi, MQTT broker, Zigbee network.]
- **Platforms & Apps:** [Home Assistant, Apple HomeKit, custom dashboard web page.]
- **Hardware Supplies:** [Specific breakout boards, sensors, fasteners, enclosures on order.]

---

## 10. Early Technical Notes (Scratchpad for L2 Architecture)

*Do not put technical implementation details into the requirements above. Jot down early engineering ideas, part suggestions, or protocol thoughts here for use during the Architecture phase.*

- *Candidate Hardware:* [e.g., ESP32-C3 SuperMini, BME280 sensor breakout]
- *Wiring / Pin Ideas:* [e.g., I2C on GPIO 8/9, ADC battery divider on GPIO 0]
- *Software / Protocol Ideas:* [e.g., ESPHome, MQTT topic structure `home/sensors/patio`]
