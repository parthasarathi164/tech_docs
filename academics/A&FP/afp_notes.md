## Wind Tunnel Experiment (Velocity vs RPM) (lab exp1)

#### General formula for $V_2$
Start from Bernoulli between points 1 and 2 (same elevation, incompressible, inviscid):
$$
P_1+\tfrac{1}{2}\rho V_1^2 \;=\; P_2+\tfrac{1}{2}\rho V_2^2.
$$
Rearrange for $V_2$:
$$
V_2 \;=\; \sqrt{\,V_1^2 \;+\; \dfrac{2\,(P_1-P_2)}{\rho}\, }.
$$

**Terms:** $P_{1,2}$ = static pressures at points 1 and 2; $V_{1,2}$ = velocities; $\rho$ = fluid density.

---

#### Velocity at exit of a convergent section (use continuity)
Continuity:
$$A_1 V_1 = A_2 V_2 \quad\Rightarrow\quad V_1=\dfrac{A_2}{A_1}V_2.$$
Substitute into Bernoulli ($\Delta P\equiv P_1-P_2$):
$$
V_2^2\Big(1-\Big(\dfrac{A_2}{A_1}\Big)^2\Big) \;=\; \dfrac{2\,(P_1-P_2)}{\rho}.
$$
Thus

$$
P_1-P_2 = \rho_m\,g\,(h_2-h_1) \equiv \rho_m\,g\,\Delta h.
$$

Substitute into the velocity expression:
$$
\boxed{%
V_2 \;=\; \sqrt{\dfrac{\,2\,g\,\Delta h\,\rho_m\,}{\,\rho_a\,[\,1-(A_2/A_1)^2\,]}}.
}
$$

**Terms:**  
- $A_1, A_2$ = cross-sectional areas at the inlet (1) and exit (2) of the convergent section  
- $\rho_m$ = manometric fluid density
- $\rho_a$ = air (flowing fluid) density  
- $\Delta h = h_2 - h_1$ = difference in manometer column heights (both open to atmosphere)

---

#### Velocity from a Pitot–static probe (general form)

Pitot measures total (stagnation) pressure $P_t$ and static nearby is $P_s$.  
By Bernoulli along that streamline:

$$
P_t - P_s = \rho_m g \Delta h.
$$

Substitute into Bernoulli and solve for $V$:
$$
\rho_m g \Delta h = \tfrac{1}{2}\rho_a V^2
\quad\Rightarrow\quad
V = \sqrt{\dfrac{2\,g\,\Delta h\,\rho_m}{\rho_a}}.
$$

**Terms:**  
- $P_t$ = total (stagnation) pressure measured by Pitot opening  
- $P_s$ = static pressure from static port
- $\rho_m$ = manometric fluid density
- $\rho_a$ = air (flowing fluid) density
- $\Delta h$ = difference in manometer column heights

**Note:**  
Applies for **incompressible and inviscid** flow. For compressible or high-Mach flows, use compressible Pitot relations.

#### Difference between Static, Dynamic, and Total Pressure

| Type of Pressure                | Symbol                     | Definition / Meaning                                                   | Measurement Method                                        |
| ------------------------------- | -------------------------- | ---------------------------------------------------------------------- | --------------------------------------------------------- |
| **Static Pressure**             | $P_s$                      | Pressure exerted by fluid at rest or acting equally in all directions. | Measured by a static port (hole parallel to flow).        |
| **Dynamic Pressure**            | $q = \tfrac{1}{2}\rho V^2$ | Pressure due to fluid motion (kinetic energy per unit volume).         | Calculated from velocity or from Pitot–static difference. |
| **Total (Stagnation) Pressure** | $P_t = P_s + q$            | Pressure if fluid is brought to rest isentropically.                   | Measured by Pitot tube facing the flow.                   |

#### Steps to perform experiment

1. Start starter motor (30 rpm).
2. Start main motor, ramp to first rpm (100 rpm).
3. Wait for stable flow.
4. Record manometer readings (inclined at $30^\circ$ and straight tube).
5. Repeat for each rpm: 100, 200, 300, 400, 500.
6. Calculate $V$ for each rpm using the above formula.
7. Plot $V$ vs rpm and check for linearity.
---

>date: 11-02-2026, Wednesday

## Airfoil Nomenclature

[YouTube video](https://youtu.be/6wgrDBa-AXo) for the above concept.

---

## NACA 4, 5 & 6 digit airfoils

As airfoil design evolved to meet higher performance requirements—like reducing drag at high speeds—the NACA numbering systems became more complex to provide engineers with finer control over the geometry.

### NACA 4-Digit Airfoil Specification

This series is defined by the format **NACA MPXX** (e.g., NACA 2412).

- **M (1st Digit):** The maximum camber divided by 100. In the example $M=2$, so the camber is $0.02$ or **2% of the chord**.
- **P (2nd Digit):** The position of the maximum camber divided by 10. In the example $P=4$, so the maximum camber is at $0.4$ or **40% of the chord**.
- **XX (3rd & 4th Digits):** The thickness divided by 100. In the example $XX=12$, so the thickness is $0.12$ or **12% of the chord**.

---

### NACA 5-Digit Airfoil Specification

This series uses a slightly different logic for its digits to provide more specific aerodynamic control.

| **Digits** | **Letter** | **Example** | **Description**                                                                                                                        |
| ---------- | ---------- | ----------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| **1**      | **L**      | 2           | Controls the camber. It indicates the design coefficient of lift ($C_l$) multiplied by 3/20. In the example $L=2$, so **$C_l = 0.3$**. |
| **2**      | **P**      | 3           | The position of maximum camber divided by 20. In the example $P=3$, so maximum camber is at **$0.15$ or 15% chord**.                   |
| **3**      | **Q**      | 0           | Indicates the camber line type: **0 = normal** camber line, **1 = reflex** camber line.                                                |
| **4 & 5**  | **XX**     | 12          | The maximum thickness as a percentage. In the example $XX=12$, so the maximum thickness is **$0.12$ or 12% chord**.                    |

---

### NACA 6-Series (Laminar Flow)

These were developed during WWII to maximize **laminar flow**, which significantly reduces skin-friction drag.

- **Example:** **NACA 64-212**
- **1st Digit:** The series number (6).
- **2nd Digit:** Location of the minimum pressure point (40% of chord).
- **3rd Digit (after dash):** The design lift coefficient in tenths (0.2).
- **4th & 5th Digits:** Max thickness (12% of chord).
- **Characteristics:** Very low drag at specific "design" speeds, but the performance drops off sharply if the wing gets dirty (bugs, rain) or if the angle of attack is outside the design "bucket."

---

### Characteristics Table

| **Series**   | **Focus**   | **Stall Behavior**                                 | **Pitching Moment**                                    | **Key Characteristic**                                     |
| ------------ | ----------- | -------------------------------------------------- | ------------------------------------------------------ | ---------------------------------------------------------- |
| **4-Digit**  | Geometry    | **Soft & Gradual**: Predictable and safe.          | **Moderate**: Standard structural loads.               | Simple to design and build.                                |
| **5-Digit**  | Lift/Moment | **Abrupt**: Sharp drop in lift at critical angles. | **Extremely Low**: Minimal torsional load on the wing. | High $C_{L_{max}}$ for better takeoff/landing.             |
| **6-Series** | Efficiency  | **Sharp**: Performance drops quickly at stall.     | **High**: Requires strong tail/structural control.     | **"Drag Bucket"**: Extremely low drag during laminar flow. |

---

## The Center of Pressure (CP)

**Technical Definition:** The point at which the Leading Edge Moment ($M_{LE}$) is balanced by the normal force ($N$) is indeed called the **Center of Pressure**.

### Core Concept

- **Vector Summation:** It is the point where the entire aerodynamic force (Lift and Drag) is concentrated for the purpose of analysis.
- **Resultant Force:** At this exact point, the net aerodynamic **pitching moment is zero**.
- **Movement:** Unlike the "Aerodynamic Center" (which stays relatively fixed at 25% chord), the **CP moves** as the angle of attack changes.

### Impact on Stability

- **Forward Movement:** As you increase the angle of attack, the CP typically moves forward (toward the leading edge).
- **Aft Movement:** As the angle of attack decreases, the CP moves toward the trailing edge.
- **Structural Load:** Because the CP moves, the "torque" or twisting force on the wing spar changes during different maneuvers.

---

## Normal forces, Axial forces and Moments in an airfoil

![[IMG_20260211_200527019_HDR.jpg]]
![[IMG_20260211_200532930_HDR.jpg]]

## Aerodynamic center

The **Aerodynamic Center (AC)** is a fixed point on the airfoil's chord line where the **pitching moment remains constant** regardless of changes in the angle of attack.

### Why It Is Important

- **Constant Moment:** While the lift increases as the angle of attack increases, the change in lift acts at this point in a way that the twisting force (moment) stays the same.
- **Stability:** In subsonic flight, the AC is located approximately at the **25% chord position** (the "quarter-chord").
- **Structural Design:** Knowing that the AC is relatively fixed helps engineers design the wing's internal structure (like the main spar) to handle consistent twisting loads during flight.

---

>date: 13-01-2026, Tuesday

## downwash and its effects

![[Pasted image 20260113150844.png]]

**Induced and parasitic drag difference**

- Induced drag is a byproduct of lift (strongest at low speeds/high AoA, decreases with speed), while parasite drag is air resistance from the aircraft's shape/friction (increases with speed).

>[detailed video on induced drag and downwash](https://youtu.be/MnB6Lqr91Yc)

### 1. The Formation of Wingtip Vortices

Because a wing generates lift, there is **high pressure** on the bottom surface and **low pressure** on the top surface. At the wingtips, the air is not "contained" by the wing structure, so the high-pressure air underneath tries to curl around the tip to reach the low-pressure zone on top.

- This creates two counter-rotating spirals of air trailing behind the aircraft.
- From the **rear view** (as shown in your image):
    - The **left** vortex rotates **clockwise**.
    - The **right** vortex rotates **counter-clockwise**.

### 2. The Downwash Effect (The Middle Section)

In the region between the two wingtips (where the actual wing is located), the combined action of both vortices pushes the air **downward**.

- **Definition:** This downward component of velocity is called **Downwash** ($w$).
- **Consequence:** Downwash tilts the local relative wind downward. This means the wing "sees" the air coming from a slightly shallower angle than the actual flight path.
- **Induced Drag:** Because the lift vector is perpendicular to the _local_ relative wind, it gets tilted backward. This backward component of lift is what we call **Induced Drag**—the "price" paid for generating lift with a finite wing.

### 3. The Upwash Effect (The Outer Sections)

Outside the span of the wing, the circular motion of the vortices continues. After the air is pushed down in the center, it must move outward and then **upward** to complete the cycle.

- **"Not experienced by the wing":** Your note correctly identifies that this upwash occurs outside the physical structure of the wing. Therefore, it does not contribute to the lift or drag of the aircraft generating it.
- **Formation Flight:** This is the principle birds (and military pilots) use when flying in a "V" formation. A trailing bird will position its wing in the **upwash** of the bird in front, gaining "free" lift and reducing the effort needed to fly.

### 4. The Velocity Distribution Curve

The arrows in that image represent the **induced vertical velocity** (airflow direction and magnitude) created by the wing-tip vortices as seen from behind the aircraft.

![[Pasted image 20260113151654.png]]

#### Breakdown of the Arrow Directions

- **Downward Arrows (Downwash):** These arrows, located between the wing tips, indicate air being pushed downward. This is the **Downwash Effect**, which is a direct result of the high-pressure air from under the wing meeting the low-pressure air on top. This downward flow effectively "tilts" the lift vector backward, which creates **Induced Drag**.
- **Upward Arrows (Upwash):** These arrows are located outside the span of the wings. They represent the air being pulled upward as the vortex completes its circular rotation. As the handwritten note in the image states, this upwash is **"not experienced by the wing"** because it occurs in the air outboard of the wing tips.
- **Circular Arrows:** At the very tips of the wings, the circular arrows illustrate the **Wing-Tip Vortices** themselves. These are the actual rotating "tornadoes" of air that form as air leaks over the wing tip.

#### What the Length of the Arrows Indicates

The length of the vertical arrows corresponds to the **Velocity Distribution** curve at the bottom of the sketch:

- **Longer arrows** near the wing tips show that the induced velocity (the strength of the push) is most intense near the source of the vortex.
- **Shorter arrows** toward the center (fuselage) show that the effect of the tip vortices diminishes as you move toward the middle of the wingspan.
---
### Summary Table

| **Feature**  | **Direction** | **Impact**                                                                    |
| ------------ | ------------- | ----------------------------------------------------------------------------- |
| **Downwash** | Downward      | Reduces effective angle of attack; creates Induced Drag.                      |
| **Upwash**   | Upward        | Occurs outside the wingspan; can be used by trailing aircraft for efficiency. |
| **Vortices** | Circular      | Caused by pressure equalization at the wingtips.                              |

---

## planform geometries

![[Pasted image 20260113164154.png]]

### 1. Rectangular Planform (Straight Wing)

This is the simplest geometry to manufacture and is common on light aircraft.

- **Planform Area:** $S = b \times c$
    
- **Notes:**
    
    - $\mathbf{(*)}$ The **bottom streamline** curves **away from the fuselage** towards the wingtip due to the high-pressure air "leaking" outward toward the tips.
    - $\mathbf{(*)}$ The **top streamline** curves **towards the fuselage** because the low pressure on top draws in the air that has curled around the tips from the bottom.
    - $\mathbf{(*)}$ **Stall:** It naturally stalls at the **root first**, which is a safety feature as it provides a buffet warning to the pilot while keeping the ailerons effective at the tips.

### 2. Tapered Planform

In this design, the chord ($c$) decreases linearly from the root to the tip to improve aerodynamic efficiency and reduce structural weight.

- **Planform Area:** $S = \frac{b}{2} \cdot (c_{root} + c_{tip})$
    
- **Notes:**
    
    - $\mathbf{(*)}$ The **top streamline** curves inward toward the fuselage more strongly than a rectangular wing because the pressure gradient is steeper toward the larger root.
    - $\mathbf{(*)}$ **Stall:** Tapered wings tend to **stall at the tips first**, which can cause a sudden loss of roll control.

### 3. Swept-Back Planform

Standard for high-speed and commercial jet aircraft, where the wings are angled backward.

- **Planform Area:** Typically calculated as a tapered wing but defined by the sweep angle ($\Lambda$).
    
- **Notes:**
    
    - $\mathbf{(*)}$ The **top streamline** curves **away from the fuselage** toward the wingtips. This "spanwise flow" occurs because the air travels along the diagonal of the swept leading edge.
    - $\mathbf{(*)}$ This outward flow causes the boundary layer to "pile up" at the tips, often requiring "wing fences" to prevent early **tip stall**.

### 4. Delta Planform

A triangular wing used primarily for supersonic flight and high-performance maneuvers.

- **Planform Area:** $S = \frac{1}{2} \cdot b \cdot c_{root}$
    
- **Notes:**
    
    - $\mathbf{(*)}$ The streamlines are dominated by **Leading Edge Vortices**. At high angles of attack, air spirals tightly from the bottom, over the sharp leading edge, and onto the top surface.
    - $\mathbf{(*)}$ These **top streamlines** form a powerful "suction" spiral that generates lift even at very high angles of attack where other wings would fail.

### 5. Elliptical Planform

This is the "ideal" aerodynamic shape, famously used on the WWII Spitfire.

- **Planform Area:** $S = \frac{\pi}{4} \cdot b \cdot c_{root}$
    
- **Notes:**
    
    - $\mathbf{(*)}$ The streamlines are remarkably uniform; it produces a constant downwash velocity across the entire span.
    - $\mathbf{(*)}$ This results in the **minimum possible induced drag** for a given wingspan, though it is very difficult to manufacture.

---
### Summary Table for Quick Reference

| **Geometry**    | **Top Streamline Curve**  | **Primary Advantage**   |
| --------------- | ------------------------- | ----------------------- |
| **Rectangular** | Inward (toward root)      | Simple / Safe stall     |
| **Tapered**     | Strong Inward             | Weight / Efficiency     |
| **Swept**       | **Outward** (toward tips) | High-speed (Transonic)  |
| **Delta**       | Spiraling Inward          | Supersonic / High AoA   |
| **Elliptical**  | Uniform / Minimal         | Maximum Aero Efficiency |

---
## types of drag

### **1. Total Drag in Subsonic Flow**

For a finite wing flying at subsonic speeds, the total drag is the sum of three distinct physical components:

- **Skin Friction Drag ($D_f$):** This arises from the viscous resistance of the air sliding over the wing's surface within the boundary layer.
- **Pressure Drag ($D_p$):** Also known as form drag, this is caused by the pressure imbalance between the front (leading edge) and the rear (trailing edge) of the wing.
- **Induced Drag ($D_i$):** This is a penalty for generating lift. It is caused by **wingtip vortices** that create a downward component of velocity (downwash), tilting the lift vector backward. The coefficient is expressed as $C_{D,i} = \frac{D_i}{q_\infty S}$.

> **Key Definition:** The combination of Skin Friction Drag and Pressure Drag is referred to as **Profile Drag**.

---
### **2. The Case of the "Infinite Wing" (Airfoil)**

If we consider an infinite wing (a 2D airfoil section with no ends), the airflow is purely two-dimensional:

- Because there are no wingtips, wingtip vortices cannot form.
- Consequently, **Induced Drag is zero** ($D_i = 0$).
- The total drag for an airfoil consists only of Profile Drag ($C_d = \frac{D_f + D_p}{q_\infty S}$).

---
### **3. Drag in High-Speed (Supersonic) Flow**

When the aircraft moves at speeds where shock waves begin to form on the body, a new component is introduced:

- **Wave Drag:** This drag is caused by the energy loss across shock waves that form during high-speed flight.
- **Total Drag Equation:** For a supersonic finite wing, the total drag is the summation of **Profile Drag**, **Induced Drag**, and **Wave Drag**.
---
### **Summary Table**

| **Wing/Flow Type**         | **Drag Components**               | **Formula / Notation**        |
| -------------------------- | --------------------------------- | ----------------------------- |
| **Infinite Wing (2D)**     | Skin Friction + Pressure          | $C_d = \text{Profile Drag}$   |
| **Subsonic Finite Wing**   | Profile Drag + Induced Drag       | $D_{total} = D_f + D_p + D_i$ |
| **Supersonic Finite Wing** | Profile + Induced + **Wave Drag** | Sum of all four components    |

---
## terms related to wing and its aerodynamics
### **1. Wing Twist: Definitions**

Wing twist is a design feature where the angle of attack or the airfoil section changes along the wingspan to improve aerodynamic performance and stall characteristics.

- **Washout:** This is a spanwise twist where the **angle of incidence decreases** from the wing root to the wingtip. Its primary purpose is to ensure the wing root stalls before the wingtip, allowing the pilot to maintain aileron control during a stall.
- **Washin:** This is the opposite of washout, where the **angle of incidence increases** from the root to the wingtip. This is rarely used in standard aircraft design as it can lead to dangerous tip-stall characteristics.
---
### **2. Types of Wing Twist**

Twist can be achieved through two different methods:

#### **Geometric Twist**

Geometric twist is a physical change in the angle of the airfoil sections along the span.

- **Definition:** It is the actual change in the **geometric angle of incidence** of the airfoil sections from the root to the tip.
- **Mechanism:** The wing is physically twisted during manufacturing so that the chord line of the tip airfoil is at a different angle relative to the chord line of the root airfoil.

#### **Aerodynamic Twist**

Aerodynamic twist is achieved by changing the shape of the airfoil section rather than physically twisting the wing.

- **Definition:** It is the change in the **zero-lift angle of attack** along the span.
- **Mechanism:** This is done by using different airfoil profiles at various sections of the wing (e.g., a highly cambered airfoil at the root and a less cambered one at the tip). Even if the geometric angle remains the same, the aerodynamic behavior changes.
---
### **3. Connection to Your Notes**

The concepts above relate directly to the drag and flow behaviors mentioned in your uploaded documents:

- **Induced Drag:** By using washout, designers can create a more **elliptical lift distribution**, which minimizes induced drag ($C_{D,i}$).
- **Wingtip Vortices:** Twist helps manage the strength of the flow "leak" from the bottom to the top surface at the tips, which is the root cause of wingtip vortices.
- **Helmholtz Theorem:** The strength of the vortex filament must remain constant along its length; aerodynamic twist is a tool used to control how that vortex strength is distributed across the physical wing.

---
### **Summary Table**

| **Term**              | **Primary Feature**           | **Main Purpose**                          |
| --------------------- | ----------------------------- | ----------------------------------------- |
| **Washout**           | Angle decreases toward tip    | Safety (prevents tip stall)               |
| **Washin**            | Angle increases toward tip    | Specialized aerodynamic tuning            |
| **Geometric Twist**   | Physical rotation of sections | Adjusts local Angle of Attack             |
| **Aerodynamic Twist** | Change in airfoil shape       | Adjusts zero-lift angle/lift distribution |

---

>date: 12-02-2026, Thursday

## Flight path of an airplane / Mission profile

![[Pasted image 20260212150829.png]]

## Aerodynamic Forces

![[Pasted image 20260212151007.png]]

## Temperature - Altitude graph

![[Pasted image 20260212151447.png]]

## ISA Sea Level Values (SI Units)

The following table provides the International Standard Atmosphere (ISA) values at Mean Sea Level (MSL) using strictly SI units.

| **Property**                    | **Symbol** | **Value (SI Units)**                                  |
| ------------------------------- | ---------- | ----------------------------------------------------- |
| **Temperature**                 | $T_0$      | **$288.15\text{ K}$** ($15^\circ\text{C}$)            |
| **Pressure**                    | $P_0$      | **$101,325\text{ Pa}$** ($101.325\text{ kPa}$)        |
| **Density**                     | $\rho_0$   | **$1.225\text{ kg/m}^3$**                             |
| **Speed of Sound**              | $a_0$      | **$340.29\text{ m/s}$**                               |
| **Acceleration due to Gravity** | $g_0$      | **$9.80665\text{ m/s}^2$**                            |
| **Dynamic Viscosity**           | $\mu_0$    | **$1.789 \times 10^{-5}\text{ kg/(m}\cdot\text{s)}$** |
| **Gas Constant (for dry air)**  | $R$        | **$287.05\text{ J/(kg}\cdot\text{K)}$**               |

---

## Atmospheric calculations

The equations in the provided image are the three fundamental building blocks for calculating how atmospheric properties change with altitude.

---

### 1. Hydrostatic Equation

$$\frac{dp}{dh} = -\rho g$$

- **What it indicates:** This describes the relationship between a change in pressure ($dp$) and a change in altitude ($dh$).
- **The Logic:** The negative sign indicates that as altitude ($h$) increases, atmospheric pressure ($p$) decreases. This is because there is less weight of air pressing down from above as you go higher.

### 2. Perfect Gas Law (Equation of State)

$$P = \rho RT$$

- **What it indicates:** This relates the pressure ($P$), density ($\rho$), and temperature ($T$) of the air.
- **The Logic:** It treats air as an ideal gas. $R$ is the specific gas constant for air. It allows you to calculate any one of these three variables if you know the other two.

### 3. Lapse Rate Equation

$$T = T_0 - Lh$$

- **What it indicates:** This calculates the temperature ($T$) at a specific altitude ($h$) based on the sea-level temperature ($T_0$).
- **The Logic:** In the ISA model, temperature is assumed to drop linearly as you climb through the troposphere. $L$ is the **lapse rate** (standardized at $0.0065\text{ K/m}$ or $6.5^\circ\text{C/km}$).

---

By combining these three equations, you can derive the formulas needed to find the exact pressure and density at any altitude for your wing analysis.


## Formulae required for numericals

For your aerodynamic calculations and solver setups, it is often most useful to express these as **non-dimensional ratios**. Here is the breakdown for the Troposphere and the Isothermal layer (Stratosphere) using that specific format.

### 1. Troposphere (Lapse Rate $L = 0.0065 \text{ K/m}$)

In this region, the temperature follows the equation $T = T_0 - Lh$. The pressure and density ratios are derived by substituting the temperature relationship into the hydrostatic and perfect gas equations.

- **Pressure Ratio:**
$$\frac{P}{P_0} = \left( \frac{T}{T_0} \right)^{\frac{g}{RL}}$$
- **Density Ratio:**
$$\frac{\rho}{\rho_0} = \left( \frac{T}{T_0} \right)^{\left( \frac{g}{RL} - 1 \right)}$$

---

### 2. Isothermal Stratosphere (Lapse Rate $L = 0$)

In this layer, the temperature is constant ($T = T_1$), so the ratio $T/T_0$ is no longer the driving variable for change. Instead, the ratios are calculated relative to the conditions at the **Tropopause** ($h_1 = 11,000 \text{ m}$), using an exponential decay based on the change in altitude ($\Delta h = h - h_1$).

- **Pressure Ratio:**
$$\frac{P}{P_1} = e^{\left[ -\frac{g}{RT}(h - h_1) \right]}$$
- **Density Ratio:**
$$\frac{\rho}{\rho_1} = e^{\left[ -\frac{g}{RT}(h - h_1) \right]}$$

_(Note: In an isothermal layer, the pressure ratio and density ratio are identical because temperature does not change.)_

---

### Quick Reference Table

| **Layer**        | **Lapse Rate (L)** | **Ratio Formula Type**        | **Physical Behavior**                       |
| ---------------- | ------------------ | ----------------------------- | ------------------------------------------- |
| **Troposphere**  | $6.5 \text{ K/km}$ | **Power Law** ($T/T_0$ based) | Pressure drops faster than temperature.     |
| **Stratosphere** | $0 \text{ K/km}$   | **Exponential** ($e$ based)   | Pressure and density drop at the same rate. |

---

## Difference between TAS & EAS

To understand why engineers use different types of airspeed, it helps to think of the difference between how many air molecules the aircraft is actually hitting (**Equivalent**) versus how fast it is physically moving over the ground in a no-wind condition (**True**).

### True Airspeed (TAS)

**True Airspeed** is the actual physical speed of the aircraft through the air mass. It is the velocity you would measure if you were sitting on a particle of air as the plane flew past.

- **Dependency:** TAS depends directly on the density of the air.
- **Altitude Effect:** As you climb higher into thinner air (lower density), you must fly at a higher TAS to maintain the same aerodynamic pressure on the wings.
- **Use Case:** Essential for flight planning and navigation to determine how long it will take to reach a destination.

### Equivalent Airspeed (EAS)

**Equivalent Airspeed** is a theoretical speed that represents the airspeed at sea level that would produce the same **dynamic pressure** as the current flight condition.

- **Aerodynamic Feel:** The aircraft's structural loads, lift, and stall behavior are almost entirely dependent on EAS, not TAS.
- **Compressibility:** EAS is essentially Calibrated Airspeed (CAS) corrected for compressibility effects at high speeds and high altitudes.
- **Use Case:** Used by structural engineers and test pilots to ensure the aircraft doesn't exceed its design limits (like wing flutter) at high altitudes.

---

### Key Differences: TAS vs. EAS

|**Feature**|**Equivalent Airspeed (EAS)**|**True Airspeed (TAS)**|
|---|---|---|
|**Definition**|Speed at sea level creating the same dynamic pressure.|Physical speed of the aircraft through the air mass.|
|**Formula Relationship**|$EAS = TAS \sqrt{\frac{\rho}{\rho_0}}$|$TAS = \frac{EAS}{\sqrt{\sigma}}$ (where $\sigma$ is density ratio).|
|**Effect of Altitude**|Remains relatively constant for a specific "feel" or stall point.|**Increases** with altitude for a constant EAS.|
|**Primary Use**|Structural limits and aerodynamic stall speeds.|Navigation, flight planning, and performance timing.|
|**Density Influence**|Mathematically removes the effect of non-standard density.|Directly accounts for the actual local air density.|

### Why this matters for your wing analysis

In your modal analysis, the **dynamic pressure ($q = \frac{1}{2}\rho V^2$)** is the actual load applied to the wing. Because $EAS$ is directly related to $\sqrt{q}$, calculating your wing's vibration modes at $12\text{ km}$ requires converting your target TAS back to EAS to understand the actual structural "force" hitting the wing.

---

## Unit 3 - steady flight numericals

### problem 1

![[Pasted image 20260214131618.png]]

This is a classic performance analysis problem. To solve it, we first need to extract the aircraft's geometric parameters from the given flight conditions and then apply the fundamental equations of aerodynamics.

#### Given Data:

- **Weight ($W$):** $3,60,000 \text{ N}$
- **Wing Span ($b$):** $35 \text{ m}$
- **Wing Loading ($W/S$):** $3000 \text{ N/m}^2$
- **Span Efficiency Factor ($e$):** $0.9$
- **Zero-lift Drag Coefficient ($C_{D,0}$):** $0.019$

---

#### Step 1: Preliminary Geometric Calculations

Before finding the drag polar, we need the **Wing Area ($S$)** and the **Aspect Ratio ($AR$)**.

1. **Wing Area ($S$):**
    
    $$S = \frac{W}{W/S} = \frac{360,000}{3000} = 120 \text{ m}^2$$
    
2. **Aspect Ratio ($AR$):**
    
    $$AR = \frac{b^2}{S} = \frac{35^2}{120} = \frac{1225}{120} \approx 10.21$$
    

> **Reason:** The drag polar depends heavily on the Induced Drag, which is a function of the wing's geometry (Aspect Ratio). We must calculate $S$ and $AR$ first to find the induced drag constant $K$.

---

#### i. Drag Polar Equation

The drag polar is represented by the equation: $C_D = C_{D,0} + K C_L^2$.

1. **Calculate the Induced Drag Constant ($K$):**
    
    $$K = \frac{1}{\pi \cdot AR \cdot e} = \frac{1}{3.14159 \cdot 10.21 \cdot 0.9} \approx 0.0346$$
    
2. **Formulate the Equation:**
    
    $$C_D = 0.019 + 0.0346 C_L^2$$
    

> **Reason:** The drag polar defines the total drag coefficient as the sum of parasite drag (constant) and induced drag (which varies with the square of the lift). Calculating $K$ allows us to model how drag increases as the aircraft generates more lift.

---

#### ii. Minimum Drag ($D_{min}$)

In steady level flight, minimum drag occurs when **Parasite Drag equals Induced Drag** ($C_{D,0} = K C_L^2$).

1. **Find $C_L$ at Minimum Drag ($C_{L,Dmin}$):**
    
    $$C_{L,Dmin} = \sqrt{\frac{C_{D,0}}{K}} = \sqrt{\frac{0.019}{0.0346}} \approx 0.741$$
    
2. **Calculate Maximum Lift-to-Drag Ratio $(L/D)_{max}$:**
    
    At minimum drag, total $C_D = 2 \cdot C_{D,0} = 2 \cdot 0.019 = 0.038$.
    
    $$(L/D)_{max} = \frac{C_{L,Dmin}}{C_{D,Dmin}} = \frac{0.741}{0.038} \approx 19.5$$
    
3. **Calculate Minimum Drag Force:**
    
    Since Lift ($L$) = Weight ($W$) in level flight:
    
    $$D_{min} = \frac{W}{(L/D)_{max}} = \frac{360,000}{19.5} \approx 18,462 \text{ N}$$
    

> **Reason:** Minimum drag occurs at the most aerodynamically efficient point of flight. By setting the two drag components equal, we find the specific lift coefficient ($C_L$) that results in the lowest total drag force for a given weight.

---

#### iii. Velocity for Minimum Drag ($V_{Dmin}$)

We use the Lift equation to find the speed required to produce the weight at the $C_{L,Dmin}$ calculated above. We will assume standard sea-level density ($\rho = 1.225 \text{ kg/m}^3$).

$$L = W = \frac{1}{2} \rho V^2 S C_L$$

$$V_{Dmin} = \sqrt{\frac{2W}{\rho S C_{L,Dmin}}} = \sqrt{\frac{2 \cdot 360,000}{1.225 \cdot 120 \cdot 0.741}}$$

$$V_{Dmin} = \sqrt{\frac{720,000}{108.927}} \approx 81.3 \text{ m/s}$$

> **Reason:** To fly at the minimum drag point, the pilot must maintain a specific airspeed. If the aircraft flies faster, parasite drag dominates; if it flies slower, induced drag dominates. This calculation identifies that "sweet spot" velocity for the given weight and altitude.

---

### problem 2

![[Pasted image 20260214131805.png]]

This problem focuses on finding the optimal performance point where the aircraft is most aerodynamically efficient. For a Steady Level Flight (SLF), the thrust required ($T_R$) is exactly equal to the total drag ($D$).

#### Given Data:

- **Weight ($W$):** $2,50,000 \text{ N}$
- **Wing Area ($S$):** $86.5 \text{ m}^2$
- **Drag Polar:** $C_D = 0.016 + 0.04 C_L^2$
- Zero-lift Drag Coefficient ($C_{D,0}$) = $0.016$
- Induced Drag Constant ($K$) = $0.04$

---

#### i. Minimum Thrust Required ($T_{R,min}$)

In steady level flight, minimum thrust is required when the aircraft is flying at its minimum drag condition. This occurs when the parasite drag and induced drag are equal ($C_{D,0} = K C_L^2$).

1. **Calculate $C_L$ for Minimum Drag ($C_{L,md}$):**
    
    $$C_{L,md} = \sqrt{\frac{C_{D,0}}{K}} = \sqrt{\frac{0.016}{0.04}} = \sqrt{0.4} \approx 0.6325$$
    
2. **Calculate $C_D$ at this condition ($C_{D,md}$):**
    
    Since $C_{D,0}$ and induced drag are equal at this point:
    
    $$C_{D,md} = 2 \cdot C_{D,0} = 2 \cdot 0.016 = 0.032$$
    
3. **Find Maximum Lift-to-Drag Ratio $(L/D)_{max}$:**
    
    $$(L/D)_{max} = \frac{C_{L,md}}{C_{D,md}} = \frac{0.6325}{0.032} \approx 19.76$$
    
4. **Calculate Minimum Thrust ($T_{R,min}$):**
    
    In SLF, $T_R = D$. Therefore, $T_{R,min} = D_{min}$.
    
    $$T_{R,min} = \frac{W}{(L/D)_{max}} = \frac{250,000}{19.76} \approx 12,652 \text{ N}$$
    

> **Reason:** To minimize fuel flow in a jet aircraft during cruise, you want to operate at the point of minimum drag. By finding the ratio of how much lift (weight) we get for every unit of drag, we can determine the exact force the engines must produce to maintain level flight.

---

#### ii. Corresponding TAS at Sea Level and 5 km

To find the True Airspeed (TAS), we rearrange the lift equation: $W = \frac{1}{2} \rho V^2 S C_L$. We'll use the $C_{L,md}$ found in Step 1.

##### At Sea Level ($\rho_0 = 1.225 \text{ kg/m}^3$):

$$V_{SL} = \sqrt{\frac{2W}{\rho_0 S C_{L,md}}} = \sqrt{\frac{2 \cdot 250,000}{1.225 \cdot 86.5 \cdot 0.6325}}$$

$$V_{SL} = \sqrt{\frac{500,000}{67.02}} \approx 86.37 \text{ m/s}$$

##### At 5 km Altitude:

First, we need the density at $5 \text{ km}$. Using the International Standard Atmosphere (ISA) model:

$$\rho_{5km} \approx 0.736 \text{ kg/m}^3$$

$$V_{5km} = \sqrt{\frac{2W}{\rho_{5km} S C_{L,md}}} = \sqrt{\frac{2 \cdot 250,000}{0.736 \cdot 86.5 \cdot 0.6325}}$$

$$V_{5km} = \sqrt{\frac{500,000}{40.26}} \approx 111.45 \text{ m/s}$$

> **Reason:** While the _minimum thrust_ required doesn't change with altitude (because the weight and the $L/D$ ratio remain constant), the _speed_ required to generate that lift does change. As the air gets thinner (lower density), the aircraft must fly faster to produce the same amount of lift to support its weight.

---

### problem 3

![[Pasted image 20260214134157.png]]

#### Problem 1: Straight Wing Analysis

This problem requires finding the induced drag coefficient and the overall efficiency ratio for a specific wing configuration.

#### Given Data:

- **Aspect Ratio ($AR$):** $6$
- **Lift Coefficient ($C_L$):** $0.648$ (at $\alpha = 6^\circ$)
- **Span Efficiency Factor ($e$):** $0.95$
- **Zero-lift Drag Coefficient ($C_{D,0}$):** $0.0074$

#### Steps:

1. **Calculate Induced Drag Coefficient ($C_{D,i}$):**
    
    $$C_{D,i} = \frac{C_L^2}{\pi \cdot AR \cdot e} = \frac{0.648^2}{3.14159 \cdot 6 \cdot 0.95} = \frac{0.4199}{17.907} \approx 0.0234$$
    
    > **Reason:** Induced drag is the "drag due to lift." Since we have the lift coefficient and the wing's geometry (Aspect Ratio), we can determine how much extra drag is generated by the wingtip vortices.
    
2. **Calculate Total Drag Coefficient ($C_D$):**
    
    $$C_D = C_{D,0} + C_{D,i} = 0.0074 + 0.0234 = 0.0308$$
    
    > **Reason:** The total drag is simply the sum of the parasite drag (fixed) and the induced drag (variable).
    
3. **Calculate $(L/D)$ Ratio:**
    
    $$(L/D) = \frac{C_L}{C_D} = \frac{0.648}{0.0308} \approx 21.04$$
    
    > **Reason:** This ratio represents the aerodynamic efficiency. For every unit of drag produced, the wing generates approximately $21$ units of lift.
    

---

### Problem 2: Flight at Sea Level

This problem asks for the actual **Induced Drag force ($D_i$)** in Newtons for an aircraft in specific flight conditions.

#### Given Data:

- **Mass ($m$):** $2270 \text{ kg} \rightarrow \text{Weight } (W) = 2270 \cdot 9.81 = 22,268.7 \text{ N}$
- **Span ($b$):** $15.25 \text{ m}$
- **Velocity ($V$):** $145 \text{ km/hr} \div 3.6 \approx 40.28 \text{ m/s}$
- **Density ($\rho$):** $1.225 \text{ kg/m}^3$ (Sea Level)
- **Note:** Since $e$ is not provided, we assume an ideal elliptical lift distribution ($e = 1$) for the calculation.

#### Steps:

1. **Calculate Induced Drag Force ($D_i$):**
    
    In steady level flight, Lift ($L$) = Weight ($W$). The formula for induced drag force is:
    
    $$D_i = \frac{L^2}{\frac{1}{2} \rho V^2 \pi b^2 e}$$
    
    $$D_i = \frac{22,268.7^2}{0.5 \cdot 1.225 \cdot 40.28^2 \cdot 3.14159 \cdot 15.25^2 \cdot 1}$$
    
2. **Solve the Denominator:**
    
    $$D_i = \frac{495,895,000}{0.5 \cdot 1.225 \cdot 1622.48 \cdot 3.14159 \cdot 232.56}$$
    
    $$D_i = \frac{495,895,000}{725,604} \approx 683.4 \text{ N}$$
    

> **Reason:** Unlike the coefficient ($C_{D,i}$), the actual induced drag force is inversely proportional to the square of the velocity ($V^2$). Because the aircraft is flying relatively slowly ($145 \text{ km/hr}$), it must operate at a high angle of attack to support its weight, resulting in significant induced drag.

---

## Unit 4 numericals

### **Problem 1**

**Given:** $W = 72,000 \text{ N}$, $T_{max} = 28,000 \text{ N}$

- **(a) Thrust-to-weight ratio:**
    
    $$\frac{T}{W} = \frac{28,000}{72,000} \approx \mathbf{0.389}$$
    
- **(b) Acceleration capability:**
    
    A higher $T/W$ ratio increases the **excess thrust** ($T - D$). Since $a = \frac{T - D}{m}$, a higher ratio directly results in a higher rate of acceleration in level flight.
    
- **(c) Minimum thrust-to-weight ratio for level flight:**
    
    This occurs at the minimum drag condition ($D_{min}$):
    
    $$\left( \frac{T}{W} \right)_{min} = \frac{1}{(L/D)_{max}}$$
    

---

### **Problem 2**

**Given:** $S = 35 \text{ m}^2$, $C_{D,0} = 0.018$, $AR = 7.5$, $e = 0.92$

- **Induced drag constant ($K$):**
    
    $$K = \frac{1}{\pi \cdot AR \cdot e} = \frac{1}{\pi \cdot 7.5 \cdot 0.92} \approx 0.0461$$
    
- **(a) Lift coefficient at maximum L/D:**
    
    $$C_L = \sqrt{\frac{C_{D,0}}{K}} = \sqrt{\frac{0.018}{0.0461}} \approx \mathbf{0.625}$$
    
- **(b) Maximum L/D ratio:**
    
    At $(L/D)_{max}$, $C_D = 2 \cdot C_{D,0} = 0.036$.
    
    $$\left( \frac{L}{D} \right)_{max} = \frac{0.625}{0.036} \approx \mathbf{17.36}$$

- **(c) Explain why maximum L/D is critical for cruise performance:** 

Maximum $L/D$ (Lift-to-Drag ratio) is critical for cruise performance for the following reasons:

- **Maximum Range**: For jet aircraft, flying at maximum $L/D$ allows the aircraft to cover the greatest distance for a given amount of fuel.
- **Minimum Fuel Consumption**: It is the point of **minimum total drag**, which means the engines need to produce the least amount of thrust to maintain steady level flight.
- **Aerodynamic Efficiency**: It represents the "sweet spot" where the aircraft is most aerodynamically efficient, balancing the trade-off between parasite drag and induced drag.

---

### Problem 3

#### (a) Derivation of the Total Drag Equation

To show that total drag ($D$) can be expressed in terms of weight ($W$) and velocity ($V$) for steady level flight, we combine the fundamental drag equation with the drag polar and lift equations.

1. **Fundamental Drag Equation:**
    
    $$D = \frac{1}{2} \rho V^2 S C_D$$
    
2. **Substitute the Drag Polar:**
    
    The total drag coefficient is $C_D = C_{D,0} + \frac{C_L^2}{\pi e AR}$. Substituting this into the equation above gives:
    
    $$D = \frac{1}{2} \rho V^2 S \left( C_{D,0} + \frac{C_L^2}{\pi e AR} \right)$$
    
3. **Substitute the Lift Coefficient ($C_L$):**
    
    For steady level flight, $C_L = \frac{2W}{\rho V^2 S}$. Squaring this gives $C_L^2 = \frac{4W^2}{(\rho V^2 S)^2}$. Substituting this into the drag equation:
    
    $$D = \frac{1}{2} \rho V^2 S C_{D,0} + \frac{1}{2} \rho V^2 S \left( \frac{4W^2}{(\rho V^2 S)^2 \pi e AR} \right)$$
    
4. **Simplify to Final Form:**
    
    $$D = \frac{1}{2} \rho V^2 S C_{D,0} + \frac{2W^2}{\rho V^2 S \pi e AR}$$
    

---

#### (b) Drag Components and Speed Dependencies

The derived equation identifies two primary types of drag, each reacting differently to changes in velocity:

- **Parasite Drag ($\frac{1}{2} \rho V^2 S C_{D,0}$):** This component is **directly proportional to the square of the velocity ($V^2$)**. It increases as the aircraft speeds up due to skin friction and pressure differences.
- **Induced Drag ($\frac{2W^2}{\rho V^2 S \pi e AR}$):** This component is **inversely proportional to the square of the velocity ($\frac{1}{V^2}$)**. It is highest at low speeds when the aircraft must maintain a high angle of attack to generate enough lift to support its weight.

---

#### (c) Minimum Drag Condition

Total drag reaches its minimum value at the speed where **Parasite Drag is equal to Induced Drag**. At this point, the aircraft is operating at its maximum aerodynamic efficiency, often denoted as the maximum lift-to-drag ratio ($(L/D)_{max}$).

---

### Problem 4: Aircraft Ceilings

#### (a) Absolute Ceiling

The absolute ceiling is the theoretical maximum altitude at which an aircraft can maintain steady level flight. At this altitude, the maximum power available from the engines exactly matches the minimum power required to stay airborne.

- **Reason:** As altitude increases, air density decreases, which reduces engine thrust/power. Eventually, the excess power drops to zero, meaning the maximum Rate of Climb ($R/C$) is **$0 \text{ m/s}$ or $0 \text{ fpm}$**.
    

#### (b) Service Ceiling

The service ceiling is the practical maximum altitude where the aircraft can still maintain a small, steady rate of climb.

- **Typical Value:** For propeller-driven aircraft, it is the altitude where the max $R/C$ drops to **$100 \text{ fpm}$ ($0.5 \text{ m/s}$)**. For jet aircraft, a value of **$500 \text{ fpm}$** is often used.
    
- **Reason:** Reaching the absolute ceiling takes an infinite amount of time as the climb rate approaches zero; the service ceiling provides a measurable limit for safe operation.
    

#### (c) Operational Relevance

The service ceiling is more relevant for planning because it ensures the pilot has a "safety margin" of excess power.

- **Reason:** Flying at the absolute ceiling leaves no room for maneuvers or atmospheric changes (like turbulence or downdrafts). The service ceiling ensures the aircraft can still climb effectively if needed for safety or traffic ATC requirements.
    

---

### Problem 5: Power Required ($P_R$)

#### (a) Physical Meaning of Terms

The equation $P_R = \frac{1}{2}\rho V^3 S C_{D,0} + \frac{2W^2}{\rho V S \pi e AR}$ consists of two distinct power components:

1. **Parasite Power ($\frac{1}{2}\rho V^3 S C_{D,0}$):** This is the power needed to overcome parasite drag (skin friction and shape). It increases with the **cube of velocity ($V^3$)**.
    
2. **Induced Power ($\frac{2W^2}{\rho V S \pi e AR}$):** This is the power needed to overcome induced drag (drag due to lift). It is **inversely proportional to velocity ($1/V$)**.
    

#### (b) Power Required Curve Features

The sketch of the $P_R$ curve is typically **U-shaped** (or "J-shaped").

- **Minimum Point ($P_{R,min}$):** The lowest point of the curve indicates the speed for maximum endurance (staying in the air the longest).
    
- **Shape:** At low speeds, the curve is high due to high induced power. At high speeds, the curve rises steeply due to parasite power.
    
- **Reason:** The total power is the sum of a term that increases with speed and a term that decreases with speed, creating a unique minimum point.
    

#### (c) Increase at Low and High Speeds

- **At High Speeds:** Power required increases because parasite drag grows with the square of speed, and since $Power = Force \times Velocity$, the power required scales with **$V^3$**. The engines must work exponentially harder to "push" through the air.
    
- **At Low Speeds:** To fly slowly in level flight, the aircraft must fly at a very high Angle of Attack ($AoA$). This creates massive wingtip vortices (induced drag). Because speed is low, the aircraft is less efficient at generating lift, requiring more power to overcome this **induced drag**.

---

### Problem 6

#### (a) Calculate the Specific Excess Power ($P_s$)

Specific excess power is defined as the excess power per unit weight of the aircraft. It represents the energy rate available for climbing or accelerating.

- **Formula:** $P_s = \frac{P_A - P_R}{W}$
    
- **Calculation:** $P_s = \frac{950,000\text{ W} - 650,000\text{ W}}{55,000\text{ N}} = \frac{300,000}{55,000} \approx \mathbf{5.45\text{ m/s}}$
    
- **Reason:** By subtracting the power required for level flight ($P_R$) from the total power available ($P_A$), we find the surplus power. Dividing by weight translates this surplus into a performance metric independent of aircraft size.
    

#### (b) Determine the Rate of Climb ($R/C$)

For an aircraft in a steady, non-accelerated climb, the specific excess power is numerically equal to the vertical rate of climb.

- **In m/s:** $R/C = P_s \approx \mathbf{5.45\text{ m/s}}$
    
- **In m/min:** $5.45\text{ m/s} \times 60 \approx \mathbf{327\text{ m/min}}$
    
- **Reason:** Power is the rate of doing work. In a climb, the excess power is used to do work against gravity by increasing the aircraft's potential energy (altitude).
    

#### (c) Variation with Altitude and Operational Significance

- **Variation:** $P_s$ typically **decreases as altitude increases**. This is because air density drops, which reduces the maximum power available ($P_A$) from the engines more rapidly than it reduces the power required ($P_R$).
    
- **Operational Significance:** It defines the aircraft's **maneuverability and climb limits**. When $P_s = 0$, the aircraft has reached its absolute ceiling and can no longer climb or accelerate in level flight.
    

---

### Problem 7

#### (a) Better Range at Higher Cruise Altitudes

For a propeller-driven aircraft, the Breguet range formula shows that range ($R$) depends on aerodynamic efficiency ($C_L/C_D$), propeller efficiency ($\eta$), and specific fuel consumption ($c$).

- **Reason:** At higher altitudes, the air is less dense. To maintain the same lift at the most efficient $C_L/C_D$, the aircraft must fly at a **higher True Airspeed (TAS)**. Since range is effectively "speed $\times$ time in the air," flying faster for the same power setting allows the aircraft to cover more ground before the fuel is exhausted.
    

#### (b) Limiting Factors for High-Altitude Flight

While higher is generally better for range, two primary factors prevent flying at extremely high altitudes:

1. **Engine Power Lapse:** As air density becomes very low, naturally aspirated or even turbocharged engines eventually cannot intake enough oxygen to maintain the power required ($P_R$) for level flight.
    
2. **Stall Speed ($V_{stall}$):** Because $V_{stall}$ increases as air density decreases, eventually the minimum speed to stay airborne (stall speed) meets the maximum speed the engine can provide (power limit). This is colloquially known as the **"Coffin Corner."**

---

### Problem 8

#### (a) Velocity at which total drag is minimum ($V_{md}$)

To find the minimum drag velocity, we first determine the lift coefficient for minimum drag ($C_{L,md}$) and then solve for the corresponding speed.

1. **Calculate the induced drag constant ($K$):**
    
    $$K = \frac{1}{\pi \cdot AR \cdot e} = \frac{1}{\pi \cdot 7.2 \cdot 0.91} \approx \mathbf{0.0486}$$
    
2. **Calculate $C_{L,md}$:**
    
    Minimum drag occurs when zero-lift drag equals induced drag ($C_{D,0} = K C_L^2$).
    
    $$C_{L,md} = \sqrt{\frac{C_{D,0}}{K}} = \sqrt{\frac{0.022}{0.0486}} \approx \mathbf{0.6728}$$
    
3. **Calculate velocity ($V_{md}$):**
    
    Using the lift equation for steady level flight ($W = L = \frac{1}{2} \rho V^2 S C_L$):
    
    $$V_{md} = \sqrt{\frac{2W}{\rho S C_{L,md}}} = \sqrt{\frac{2 \cdot 65,000}{0.590 \cdot 32 \cdot 0.6728}} = \sqrt{\frac{130,000}{12.703}} \approx \mathbf{101.16 \text{ m/s}}$$
    

- **Reason:** The aircraft must fly at this specific speed to maintain the angle of attack that produces the $C_L$ required for maximum aerodynamic efficiency. At higher speeds, parasite drag dominates; at lower speeds, induced drag dominates.
    

---

#### (b) Minimum drag value and its components

1. **Calculate minimum drag coefficient ($C_{D,min}$):**
    
    Since parasite and induced drag are equal at this point:
    
    $$C_{D,min} = 2 \cdot C_{D,0} = 2 \cdot 0.022 = \mathbf{0.044}$$
    
2. **Calculate maximum lift-to-drag ratio ($(L/D)_{max}$):**
    
    $$(L/D)_{max} = \frac{C_{L,md}}{C_{D,min}} = \frac{0.6728}{0.044} \approx \mathbf{15.29}$$
    
3. **Calculate minimum drag force ($D_{min}$):**
    
    $$D_{min} = \frac{W}{(L/D)_{max}} = \frac{65,000}{15.29} \approx \mathbf{4,251 \text{ N}}$$
    
4. **Drag Components:**
    
    - **Parasite Drag:** $0.5 \cdot D_{min} \approx \mathbf{2,125.5 \text{ N}}$
        
    - **Induced Drag:** $0.5 \cdot D_{min} \approx \mathbf{2,125.5 \text{ N}}$
        

- **Reason:** By definition, the minimum drag point is the "equilibrium" between the drag caused by the aircraft's shape (parasite) and the drag caused by generating lift (induced).
    

---

#### (c) Significance of minimum drag speed for design and operations

- **Maximum Endurance:** Flying at $V_{md}$ allows a jet aircraft to stay in the air for the maximum amount of time per unit of fuel, which is critical for loitering or holding patterns.
    
- **Optimum Glide:** If an engine fails, flying at $V_{md}$ provides the shallowest glide angle, allowing the pilot to cover the maximum horizontal distance over the ground.
    
- **Climb Performance:** For jet aircraft, the maximum angle of climb occurs at $V_{md}$, as this is the point where the greatest amount of excess thrust is typically available.
    
- **Design Benchmark:** Engineers use this speed as a baseline to optimize the wing's aspect ratio and airfoil selection to ensure the aircraft cruises as close to its most efficient point as possible.

---

## Aircraft Vertical Performance and Energy Management

This section details the fundamental parameters governing how an aircraft climbs and manages its energy state, primarily focusing on the vertical flight envelope.

---

### i) Time to Climb

The **Time to Climb** is the total duration required for an aircraft to transition from an initial altitude ($h_1$) to a higher target altitude ($h_2$). This value is rarely calculated as a simple linear rate because engine performance and aerodynamic efficiency degrade as air density decreases with altitude.

**Mathematical Expression:**

Since the Rate of Climb ($RC$) is defined as the change in altitude over time ($\frac{dh}{dt}$), the total time is determined by integrating the inverse of the rate of climb across the altitude change:

$$t = \int_{h_1}^{h_2} \frac{1}{RC} dh$$

---

### ii) Maximum Climb Angle ($\theta_{max}$)

The **Climb Angle ($\theta$)** represents the steepness of the flight path relative to the horizontal plane. The **Maximum Climb Angle ($\theta_{max}$)** is the steepest possible ascent an aircraft can maintain, which is a critical metric for clearing obstacles (like mountains or buildings) immediately after takeoff.

**Mathematical Expression:**

In a steady climb, this angle is a function of the **excess thrust** ($T - D$) relative to the aircraft's weight ($W$):

$$\sin \theta = \frac{T - D}{W}$$

---

### iii) Rate of Climb ($RC$)

The **Rate of Climb** is the vertical velocity of the aircraft, typically expressed in meters per second (m/s) or feet per minute (fpm). While climb angle measures "steepness," the rate of climb measures the "speed" of altitude gain.

**Mathematical Expression:**

The rate of climb is directly proportional to the **Specific Excess Power ($P_s$)**, which is the surplus power available after overcoming level-flight drag:

$$RC = V \sin \theta = \frac{P_A - P_R}{W}$$

---

### iv) Power Required ($P_R$) and Power Available ($P_A$)

These two terms define the boundaries of the aircraft's performance envelope.

- **Power Required ($P_R$):** The power needed to overcome total drag (parasite and induced) to maintain steady level flight at a specific speed. Mathematically, $P_R = D \times V$.
    
- **Power Available ($P_A$):** The actual power provided by the propulsion system (engine and propeller/fan) at a given altitude and throttle setting.
    

**Operational Insight:**

The difference between these two values ($P_A - P_R$) is the excess power used for maneuvers and climbing. When the Power Available curve intersects the Power Required curve, the excess power becomes zero, marking the aircraft's **Absolute Ceiling**.

---

## Load Factor and Bank Angle in Level Coordinated Turns

In a level coordinated turn, the aircraft must maintain a constant altitude while turning. This requires the lift vector to be tilted to provide the necessary centripetal force while still supporting the aircraft's weight.

---

#### 1. Force Balance and Equilibrium

Consider an aircraft of weight $W$ in a steady, level coordinated turn at a bank angle $\phi$.

- **Vertical Equilibrium:** The vertical component of lift ($L \cos \phi$) must exactly balance the weight ($W$) to maintain altitude.
    
    $$L \cos \phi = W \tag{1}$$
    
- **Horizontal (Centripetal) Balance:** The horizontal component of lift ($L \sin \phi$) provides the centripetal force required to change the aircraft's direction.
    
    $$L \sin \phi = \frac{W V^2}{g R} \tag{2}$$
    
    _(where $V$ is velocity, $g$ is gravitational acceleration, and $R$ is the turn radius)_
    

---

#### 2. Derivation of Load Factor ($n$)

The load factor, often called "G-load," is defined as the ratio of the lift generated to the weight of the aircraft.

Using equation (1):

$$n = \frac{L}{W} = \frac{1}{\cos \phi}$$

**Key Insight:** As the bank angle increases, the load factor increases exponentially. At a $60^\circ$ bank, the load factor is $2$, meaning the aircraft and pilot experience twice the force of gravity.

---

#### 3. Derivation of Required Bank Angle ($\phi$)

To find the bank angle required for a specific turn radius and speed, we divide equation (2) by equation (1):

$$\frac{L \sin \phi}{L \cos \phi} = \frac{W V^2 / g R}{W}$$

$$\tan \phi = \frac{V^2}{g R}$$

**Solving for $\phi$:**

$$\phi = \tan^{-1} \left( \frac{V^2}{g R} \right)$$

---

#### 4. Summary of Operational Implications

- **Structural Limits:** Because the load factor $n$ increases with bank angle, pilots must ensure they do not exceed the aircraft's "limit load factor" during steep turns to avoid structural damage.
    
- **Stall Speed Increase:** Since the wing must produce more lift ($L = nW$) in a turn, the stall speed increases by a factor of $\sqrt{n}$.
    
- **Radius vs. Speed:** For a constant bank angle, a higher airspeed results in a much larger turn radius ($R \propto V^2$).
    

---

## The Sequence of Events During Takeoff

The takeoff phase is a critical transition where an aircraft accelerates from a standstill to a speed where the wings can generate enough lift to support the aircraft's weight. This sequence is typically divided into three distinct segments: the ground roll, the transition (rotation), and the initial climb.

---

### 1. The Ground Roll (Acceleration Phase)

This phase begins when the pilot releases the brakes and applies maximum takeoff power.

- **Force Balance:** The aircraft must overcome static friction and aerodynamic drag ($D$). The net force causing acceleration is $F = T - D - f_r$, where $T$ is thrust and $f_r$ is rolling friction.
    
- **Speed Accumulation:** As the velocity ($V$) increases, the parasite drag increases with $V^2$, while the rolling friction decreases slightly as the wings begin to generate "incidental" lift, lightening the load on the tires.
    
- **Directional Control:** Initially, the pilot uses the nose-wheel steering; as speed increases, the rudder becomes aerodynamically effective enough to maintain the centerline.
    

---

### 2. Transition and Rotation ($V_r$)

Once the aircraft reaches a pre-calculated speed known as the **Rotation Speed ($V_r$)**, the pilot initiates the transition to flight.

- **The Maneuver:** The pilot pulls back on the control column, deflecting the elevators upward. This creates a downward force on the tail, rotating the aircraft around its center of gravity.
    
- **Increase in AoA:** This rotation increases the **Angle of Attack (AoA)** of the main wings.
    
- **Lift Generation:** Because $L = \frac{1}{2} \rho V^2 S C_L$, the sudden increase in the lift coefficient ($C_L$) causes the total lift to exceed the aircraft's weight ($W$).
    

---

### 3. Lift-Off and Initial Climb ($V_{LOF}$)

The moment the wheels leave the runway is defined as **Lift-Off ($V_{LOF}$)**.

- **Clearing the Screen Height:** The takeoff is officially considered complete once the aircraft clears a "screen height" (typically $35 \text{ ft}$ for commercial jets or $50 \text{ ft}$ for small aircraft) at a safe climb speed ($V_2$).
    
- **Energy Management:** The excess thrust ($T - D$) is now used to provide a positive **Rate of Climb ($RC$)**.
    
- **Clean Configuration:** To reduce drag and improve the climb angle ($\theta$), the pilot retracts the landing gear and, eventually, the flaps/slats once a safe altitude and speed are achieved.
    

---

### Summary Table: Critical Takeoff Speeds

|**Speed Term**|**Definition**|**Operational Significance**|
|---|---|---|
|**$V_1$**|Decision Speed|Beyond this speed, the takeoff must continue even if an engine fails.|
|**$V_r$**|Rotation Speed|The speed at which the pilot raises the nose gear.|
|**$V_{LOF}$**|Lift-off Speed|The speed at which the aircraft becomes airborne.|
|**$V_2$**|Takeoff Safety Speed|The minimum speed to be maintained up to the screen height.|

---

## Aircraft Performance Derivations

This section covers the derivation of the accelerated rate of climb and the approach distance during landing, both fundamental to aircraft flight mechanics.

---

### 10 (a) Derivation of Accelerated Rate of Climb

When an aircraft is in an accelerated climb, the excess power is used for two purposes: increasing altitude (potential energy) and increasing velocity (kinetic energy).

#### 1. Energy Rate Equation

The total energy of the aircraft ($E$) is the sum of its potential and kinetic energy:

$$E = Wh + \frac{1}{2}\frac{W}{g}V^2$$

The rate of change of energy with respect to time (Specific Excess Power, $P_s$) is:

$$P_s = \frac{dE/dt}{W} = \frac{dh}{dt} + \frac{V}{g}\frac{dV}{dt}$$

#### 2. Power Balance

From the power available ($P_A$) and power required ($P_R$) relationship:

$$P_s = \frac{P_A - P_R}{W} = V\left(\frac{T-D}{W}\right)$$

#### 3. Solving for Accelerated Rate of Climb ($RC_{accel}$)

The actual vertical rate of gain in altitude is $\frac{dh}{dt}$. Rearranging the energy rate equation:

$$RC_{accel} = \frac{dh}{dt} = P_s - \frac{V}{g}\frac{dV}{dt}$$

$$RC_{accel} = V\left(\frac{T-D}{W}\right) \left[ \frac{1}{1 + \frac{V}{g}\frac{dV}{dh}} \right]$$

---

### 10 (b) Expression for Approach Distance During Landing

The landing approach distance is the horizontal distance covered while the aircraft descends from a specific "screen height" (usually $50 \text{ ft}$ or $15 \text{ m}$) to the point of touchdown.

#### 1. Approach Geometry

The aircraft follows a glide path at a constant approach angle ($\gamma_a$). Assuming a steady descent where thrust is minimal or at idle:

$$\tan \gamma_a = \frac{h_a}{S_a} \approx \sin \gamma_a \text{ (for small angles)}$$

_(where $h_a$ is screen height and $S_a$ is approach distance)_

#### 2. Force Balance in Glide

In a steady descent, the component of weight along the flight path balances the drag:

$$W \sin \gamma_a = D \implies \sin \gamma_a = \frac{D}{W} = \frac{1}{L/D}$$

#### 3. Final Expression for Approach Distance ($S_a$)

Substituting the glide relationship into the geometric equation:

$$S_a = \frac{h_a}{\tan \gamma_a} = h_a \left( \frac{L}{D} \right)_{approach}$$

**Key Factors Affecting $S_a$:**

- **Screen Height ($h_a$):** Direct linear relationship; higher clearance requires longer distance.
    
- **Aerodynamic Efficiency ($L/D$):** A "cleaner" aircraft with higher $L/D$ will have a shallower glide and require a much longer approach distance unless spoilers or airbrakes are used.

---

## Aircraft Performance and Flight Mechanics Notes

This comprehensive set of notes covers the fundamental derivations and concepts for aircraft performance, ranging from cruise efficiency to takeoff and landing maneuvers.

---

### 1. Jet Aircraft: Range and Altitude Limits

#### (a) Breguet Range Equation for Jet Propelled Airplanes

The range ($R$) of a jet aircraft depends on the fuel consumed relative to the thrust produced over time.

- **Fuel Flow Rate:** The rate of weight change is $\frac{dW}{dt} = -c_t \cdot T$, where $c_t$ is thrust-specific fuel consumption (TSFC).
    
- **Distance Integration:** Range is the integral of velocity over time: $R = \int V dt = \int \frac{V}{-c_t T} dW$.
    
- **Steady Level Flight:** Substituting $T = D$ and $L = W$, the equation becomes $R = \int \frac{V}{c_t} \frac{L}{D} \frac{dW}{W}$.
    
- **Final Formula:** Assuming constant speed and efficiency, the range is:
    
    $$R = \frac{V}{c_t} \left( \frac{L}{D} \right) \ln\left( \frac{W_0}{W_e} \right)$$
    

#### (b) Service and Absolute Ceilings

Ceilings define the vertical boundaries of the flight envelope based on engine power.

- **Absolute Ceiling:** The maximum theoretical altitude where the Rate of Climb ($RC$) is exactly zero. At this point, Power Available ($P_A$) equals Power Required ($P_R$).
    
- **Service Ceiling:** The practical altitude limit where $RC$ drops to $100 \text{ fpm}$ ($0.5 \text{ m/s}$) for propeller aircraft or $500 \text{ fpm}$ for jets.
    
- **Operational Relevance:** The service ceiling is preferred for planning as it provides a safety margin of excess power for maneuvering or countering turbulence.
    

---

### 2. Propeller Aircraft: Endurance and Vertical Performance

#### (a) Endurance ($E$) for Propeller-Driven Airplanes

Endurance is the maximum time an aircraft can stay airborne.

- **Fuel Flow:** For propellers, fuel flow depends on Power Required ($P_R$) and specific fuel consumption ($c$): $\frac{dW}{dt} = -c \cdot P_R$.
    
- **Integration:** $E = \int \frac{1}{-c P_R} dW$. Substituting $P_R = \frac{DV}{\eta}$.
    
- **Final Formula:**
    
    $$E = \frac{\eta}{c} \frac{C_L^{3/2}}{C_D} \sqrt{2 \rho S} \left( \frac{1}{\sqrt{W_e}} - \frac{1}{\sqrt{W_0}} \right)$$
    
- **Key Insight:** Maximum endurance occurs when flying at the speed for minimum power required.
    

#### (b) Performance Terminology

- **Time to Climb:** The total time to ascend, found by integrating the inverse of the rate of climb: $t = \int \frac{1}{RC} dh$.
    
- **Maximum Climb Angle ($\theta_{max}$):** The steepest ascent path, achieved when excess thrust ($T-D$) is maximized. $\sin \theta = \frac{T-D}{W}$.
    
- **Rate of Climb ($RC$):** The vertical speed of altitude gain: $RC = \frac{P_A - P_R}{W}$.
    
- **Power Required vs. Available:** $P_R$ is the power needed to overcome drag; $P_A$ is the actual power produced by the engine/propeller.
    

---

### 3. Takeoff and Maneuvering

#### (a) Takeoff Sequence of Events

Takeoff consists of three phases to transition from ground to safe flight:

1. **Ground Roll:** Acceleration from $V=0$ to $V_r$. Thrust must overcome drag and rolling friction.
    
2. **Rotation ($V_r$):** The pilot increases the angle of attack to generate lift.
    
3. **Initial Climb:** The aircraft accelerates to $V_2$ and clears the "screen height" (usually $35\text{--}50\text{ ft}$).
    

#### (b) Load Factor and Bank Angle in Coordinated Turns

In a level turn, lift must support both weight and the centripetal force.

- **Load Factor ($n$):** The ratio of lift to weight: $n = \frac{L}{W} = \frac{1}{\cos \phi}$, where $\phi$ is the bank angle.
    
- **Required Bank Angle:** Determined by the speed and radius ($R$) of the turn:
    
    $$\tan \phi = \frac{V^2}{gR}$$
    

---

### 4. Landing and Accelerated Performance

#### (a) Approach Distance ($S_a$) during Landing

The horizontal distance covered from screen height ($h_a$) to touchdown.

- **Glide Balance:** In a steady descent, $\sin \gamma_a = \frac{D}{W} = \frac{1}{L/D}$.
    
- **Distance Formula:**
    
    $$S_a = \frac{h_a}{\tan \gamma_a} = h_a \left( \frac{L}{D} \right)_{approach}$$
    

#### (b) Accelerated Rate of Climb

Considering the change in kinetic energy (acceleration) during a climb:

- **Energy Rate:** $P_s = \frac{dh}{dt} + \frac{V}{g}\frac{dV}{dt}$.
    
- **Formula:** $RC_{accel} = RC_{steady} \times \left[ \frac{1}{1 + \frac{V}{g}\frac{dV}{dh}} \right]$.
    

#### (c) The $V-n$ Diagram

A graphical representation of the aircraft's structural and aerodynamic limits.

- **X-axis:** Velocity ($V$); **Y-axis:** Load Factor ($n$).
    
- **Key Lines:** Stall limit curve, positive/negative limit load factors, and the "Corner Speed" where maximum turn performance is achieved without stalling or structural failure.

---

