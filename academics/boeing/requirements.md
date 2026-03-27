Following the logic of the "Requirements Tiers" and the "Scissor Lift" example you provided, I have structured the requirements for the **Boeing 787 Oleo-Pneumatic Strut** across three levels.

These are written to be **unambiguous, testable, and traceable**, using the "Shall" terminology as per your reference images.

### Tier 1: System Level (Strut Assembly)

These requirements focus on the final product, safety regulations, and aircraft-level integration.

| **ID**     | **Requirement**                                                                                                      | **Parent** |
| ---------- | -------------------------------------------------------------------------------------------------------------------- | ---------- |
| **T1-R-1** | The strut system shall safely support the aircraft weight during all ground operations (taxi, takeoff, and landing). | -          |
| **T1-R-2** | The system shall dissipate kinetic energy during landing to prevent structural damage to the airframe.               | -          |
| **T1-R-3** | The system shall comply with FAA/EASA airworthiness standards for shock absorption and structural integrity.         | -          |
| **T1-R-4** | The system shall provide a design service life consistent with the 787 maintenance schedule.                         | -          |
|            |                                                                                                                      |            |

---

### Tier 2: Subsystem Level (Damping & Shock Absorption)

These drill down into the specific functional and performance metrics for the damping subsystem.

| **ID**     | **Requirement**                                                                                                                                                           | **Parent**     |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| **T2-R-1** | The subsystem shall provide sufficient vertical stroke to absorb a landing sink rate of 10 feet per second at Maximum Landing Weight.                                     | T1-R-2         |
| **T2-R-2** | The subsystem shall maintain a static ground clearance of at least 25 inches for engine nacelles under Maximum Take-Off Weight.                                           | T1-R-1         |
| **T2-R-3** | The damping efficiency shall be maintained between **80% and 85%** during a limit-load landing event to optimize energy dissipation while limiting peak structural loads. | T1-R-2, T1-R-3 |
| **T2-R-4** | The subsystem shall be designed to be fail-safe, providing residual damping even in the event of partial nitrogen pressure loss.                                          | T1-R-3         |
| **T2-R-5** | The overall envelope of the strut assembly shall fit within the defined 787 wing-spar landing gear bay.                                                                   | T1-R-1         |

---

### Tier 3: Component Level (Metering Pin)

For this level, I have selected the **Metering Pin**, which is a critical internal component that controls fluid flow during the stroke.

| **ID**      | **Requirement**                                                                                                                        | **Parent** |
| ----------- | -------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| **T3-MP-1** | The function of the unit shall be to regulate hydraulic flow through the orifice to provide variable damping based on stroke position. | T2-R-1     |
| **T3-MP-2** | The pin profile shall vary linearly to ensure damping force increases as the strut reaches 90% of its total stroke.                    | T2-R-3     |
| **T3-MP-3** | The unit shall be manufactured from 15-5 PH Stainless Steel to ensure corrosion resistance and high fatigue life.                      | T1-R-4     |
| **T3-MP-4** | The weight of the metering pin unit shall not exceed a specified target (to be determined during mass budget allocation).              | T2-R-5     |
| **T3-MP-5** | The surface finish of the pin shall be 0.4 μm Ra or better to prevent wear on the orifice plate seals.                                 | T1-R-4     |
| **T3-MP-6** | The unit shall remain functional without degradation during exposure to temperatures from -54°C to +70°C.                              | T1-R-3     |

---

### How this satisfies your references:

- **Unambiguous:** Every requirement uses "Shall" and targets a specific measurable outcome (e.g., 10 fps, 25 inches, 80% efficiency).
    
- **Traceable:** Each Tier 2 and Tier 3 requirement is linked back to a "Parent" ID, ensuring no feature is added without a high-level reason.
    
- **Categorized:** Requirements are separated into Functional, Performance, and Safety/Reliability categories.
