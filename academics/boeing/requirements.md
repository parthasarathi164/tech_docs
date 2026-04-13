## Initial requirements

### Tier 1 - iteration 1

| ID         | Requirements                                                                                                                                                                          | Classification of Requirement                |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| **T1-R-1** | The thrust bench design shall comply with relevant safety standards, best engineering practices for static propulsion test benches, and all applicable lab/college safety guidelines. | **Constraint (Regulatory) + Safety**         |
| **T1-R-2** | The thrust bench design shall consider assembly, operation, maintenance, and reusability.                                                                                             | **Operational / Lifecycle (Non-functional)** |
| **T1-R-3** | The thrust bench shall provide accurate, repeatable, and reliable measurement of thrust and RPM for motor-propeller systems.                                                          | **Performance + Functional**                 |
| **T1-R-4** | Selection of materials and components with sufficient strength, stiffness, low weight, vibration damping, and low cost.                                                               | **Constraint (Design + Physical + Cost)**    |
| **T1-R-5** | The design shall ensure complete safety of operators, equipment, and surroundings during testing.                                                                                     | **Safety**                                   |
| **T1-R-6** | The thrust bench shall be modular and capable of testing the four specified motors and their recommended propellers.                                                                  | **Functional + Interface**                   |
| **T1-R-7** | The thrust bench shall support data collection, analysis, and comparison of experimental results with theoretical performance data.                                                   | **Functional**                               |

---

### Tier 2

| ID        | Requirement                                                                                                                                                                                                                                                       | Parent ID                |
| --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------ |
| **T2-R1** | The thrust bench frame and base shall safely withstand a maximum static thrust of 2250 g (factor of safety ≥ 1.5) at voltages up to 16.8 V (4S LiPo fully charged) and currents up to 40 A. The complete bench shall be lightweight (< 12 kg total) and portable. | T1-R-1 / T1-R-5 / T1-R-4 |
| **T2-R2** | The motor mounting plate shall be modular to support all four motors (RS2205-2300KV, Emax 2213-935KV, AIR 2216 II-920KV, A2212-1000KV), and propeller sizes 5” to 10”.                                                                                            | T1-R-6                   |
| **T2-R3** | The thrust measurement system shall provide thrust measurement accuracy of ±5 g or better over full scale 0–1500 g and shall be directly connected to the microcontroller.                                                                                        | T1-R-3 / T1-R-4          |
| **T2-R4** | The RPM measurement system shall provide non-contact RPM measurement with accuracy of ±50 RPM up to 25,000 RPM and shall interface directly with the microcontroller.                                                                                             | T1-R-3                   |
| **T2-R5** | The power and drive system shall support continuous current up to 40 A, voltage range 11.1–16.8 V, and simultaneous voltage and current measurement for power and efficiency (g/W) calculation.                                                                   | T1-R-6 / T1-R-7          |
| **T2-R6** | The data acquisition and control system shall perform real-time acquisition of thrust, RPM, voltage, and current and shall support data logging and transfer to PC for analysis.                                                                                  | T1-R-3 / T1-R-7          |

---

## iteration 2 of T1

## ✅ Why T1 Should Be Shortened (4 Key Points)

1. **Represents only high-level intent**
    
    - T1 should define _what the system must achieve_, not design details. ([Visure Solutions](https://visuresolutions.com/aerospace-and-defense/arp-4754/?utm_source=chatgpt.com "ARP 4754 Explained: Guidelines for Civil Aircraft and ..."))
        
2. **Maintains proper requirement hierarchy**
    
    - ARP4754 uses **top-down decomposition** (T1 → T2 → T3). ([taoscertification.com](https://taoscertification.com/wp-content/uploads/2017/05/What-is-ARP-4754A-really.pdf?utm_source=chatgpt.com "What is ARP 4754A really? Are System Engineering ..."))
        
3. **Improves traceability and clarity**
    
    - Fewer high-level requirements make mapping to lower levels easier and cleaner. ([Visure Solutions](https://visuresolutions.com/aerospace-and-defense/arp-4754/?utm_source=chatgpt.com "ARP 4754 Explained: Guidelines for Civil Aircraft and ..."))
        
4. **Reduces complexity and redundancy**
    
    - Too many T1 requirements make validation and management difficult. ([ConsuNova, Inc.](https://consunova.com/arp-4754-explained/?utm_source=chatgpt.com "ARP 4754 Explained"))
        

---

## 📋 Final Refined T1 Table - iteration 2

| ID        | Requirement                                                                                                             | Classification           |
| --------- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------ |
| **T1-R1** | The thrust bench system shall enable safe testing of motor–propeller combinations in a laboratory environment.          | Safety + Functional      |
| **T1-R2** | The system shall provide reliable measurement of key propulsion parameters including thrust, RPM, voltage, and current. | Functional + Performance |
| **T1-R3** | The system shall support data acquisition, analysis, and comparison with theoretical performance.                       | Functional               |
| **T1-R4** | The system shall be practical for laboratory use, including ease of operation, modularity, and maintainability.         | Operational / Lifecycle  |

---
