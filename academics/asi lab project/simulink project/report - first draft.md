# Project Report: Hydraulic Circuit Simulation in MATLAB Simscape

Author: [Ajith]

Date: November 30, 2025

Tool: MATLAB R2025b (Simscape Fluids, Simscape Electrical)

## 1. Objective

To design and simulate a hydraulic circuit using MATLAB Simscape based on the provided experimental learning problem. The system includes:

1. A **3-Phase Electrical Motor** driving a **Variable Displacement Pump** ($100 \text{ L/min}$, $200 \text{ bar}$).
2. A **4/3 Directional Control Valve** with a **Tandem Center** configuration.
3. A **Double-Acting Cylinder** acting on a load.
4. Detailed stagewise execution and troubleshooting of physical modeling errors.

## 2. Component Sizing & Mathematical Modeling

Before simulation, the key parameters were calculated to match the requirement of $Q = 100 \text{ L/min}$ and $P_{max} = 200 \text{ bar}$.

### 2.1 Motor Speed Calculation

A standard 4-pole industrial induction motor operating at $50 \text{ Hz}$ was selected.

$$N_s = \frac{120 \cdot f}{P} = \frac{120 \cdot 50}{4} = 1500 \text{ RPM}$$

Considering slip, the nominal speed is approx. **1450 RPM**.

### 2.2 Pump Displacement Calculation

To achieve the target flow rate at the rated motor speed:

$$Q = \frac{D \cdot n}{1000}$$

Where $Q$ is flow rate ($100 \text{ L/min}$), $n$ is shaft speed ($1450 \text{ RPM}$), and $D$ is displacement ($\text{cc/rev}$).

$$D = \frac{100 \cdot 1000}{1450} \approx 68.96 \text{ cc/rev}$$

**Selected Value:** $69 \text{ cc/rev}$.

## 3. System Construction (The Journey)

The circuit was built in stages to ensure modular accuracy.

### 3.1 Stage 1: The Power Pack (Motor & Pump)

- **Motor:** _Induction Machine (Squirrel Cage)_ configured for 3-Phase, Star Connection (Wye). Ports `a2`, `b2`, `c2` were shorted to create the Neutral point, while `a1`, `b1`, `c1` connected to the source. The Case (C) was grounded to a _Mechanical Rotational Reference_.
- **Power Source:** _Three-Phase Voltage Source_ set to $400 \text{ V}$ (Line-to-Line) and $50 \text{ Hz}$. The Neutral (n) was grounded using an _Electrical Reference_.
- **Pump:** _Variable Displacement Pump (Isothermal Liquid)_ set to $69 \text{ cc/rev}$ and Nominal Pressure $20 \text{ MPa}$. The Displacement port (D) was set to constant `1` (100% stroke).
- **Safety:** A _Pressure Relief Valve_ was added immediately after the pump, set to **200 bar**.

### 3.2 Stage 2: The Control Valve

- **Requirement:** Tandem Center (Pump unloads to Tank in neutral).
- **Implementation:** _4-Way 3-Position Directional Valve (IL)_ configured with Neutral Spool Position: **P-T Open** (Crucial for Tandem logic) and Spool Travel: $5 \text{ mm}$.
- **Control Signal:** A Simulink `Step` block commanding `5 mm` (converted to meters via PS-Simulink Converter) was used to trigger the valve at $t=1\text{s}$.

### 3.3 Stage 3: The Actuator

- **Component:** _Double-Acting Actuator (IL)_ with Port A connected to Valve A and Port B to Valve B.
- **Mechanical Setup:** The Housing (C) was grounded to a _Mechanical Translational Reference_ to prevent floating body errors. The Rod (R) was connected to a **10 kg Mass** to provide inertia ($F=ma$).

## 4. Troubleshooting & Challenges Faced

This project involved resolving several critical Simscape errors.

### Issue 1: "Solver Configuration" & "Topology" Errors

- **Problem:** The simulation failed immediately with "Topology equations" errors.
- **Root Cause:** The electrical circuit was floating, and the mechanical system lacked a reference frame.
- **Solution:** Connected **Electrical Reference** to the Voltage Source neutral, **Mechanical Rotational Reference** to the Motor/Pump casing, and **Mechanical Translational Reference** to the Cylinder casing.

### Issue 2: "Initial Conditions Solve Failed" (Hydraulic Lock)

- **Problem:** The solver crashed at $t=0$ with "Linear Algebra error."
- **Root Cause:** The cylinder started at position $0$ (against the hard stop) with incompressible fluid, causing infinite stiffness.
- **Solution:** Enabled **Entrained Air** ($0.5\%$) in _Isothermal Liquid Properties_ to allow slight compressibility, set Cylinder **Initial Position** to $0.05 \text{ m}$ (mid-stroke), and switched Solver to **Backward Euler** (Robust for stiff hydraulics).

## 5. Simulation Results

After resolving the topology and direction issues, the simulation ran successfully.

### 5.1 Verification Data (via Simscape Results Explorer)

1. **Motor Speed:** Stabilized at $\approx 151 \text{ rad/s}$ ($1450 \text{ RPM}$), confirming the electrical frequency and pole pair settings.
2. **Pump Flow:** Verified at $\approx 1.66 \times 10^{-3} \text{ m}^3/\text{s}$ ($100 \text{ L/min}$).
3. **Cylinder Motion:** At $t=0 \to 1\text{s}$, there was no motion (Valve in Tandem Center, Pump unloading to Tank). At $t>1\text{s}$, the cylinder extended smoothly as valve shifted to P-A position.

## 6. Conclusion

The hydraulic circuit was successfully modeled, satisfying all design requirements. The system correctly demonstrates the interaction between an electromechanical drive (3-phase motor) and a fluid power system (Tandem center circuit). All solver singularities were resolved by applying proper grounding, initialization, and fluid compressibility settings.
