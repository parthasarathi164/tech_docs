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

>date: 13-01-2026, Tuesday

## downwash and its effects

![[Pasted image 20260113150844.png]]

**Induced and parasitic drag difference**

- Induced drag is a byproduct of lift (strongest at low speeds/high AoA, decreases with speed), while parasite drag is air resistance from the aircraft's shape/friction (increases with speed).
---

![[Pasted image 20260113151654.png]]

>detailed video on induced drag: https://youtu.be/MnB6Lqr91yC

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

The "W" shaped curve at the bottom of your sketch represents the **magnitude and direction of the induced vertical velocity** across a horizontal line passing through the vortices.

- **Near the tips:** The velocity is highest because you are closest to the vortex core. Mathematically, according to the **Biot-Savart Law**, the induced velocity is inversely proportional to the distance from the vortex center.
- **At the center (Fuselage):** The downwash is usually slightly lower at the centerline than it is closer to the tips (depending on the lift distribution of the wing).
- **The Spikes:** The points where the curve crosses the horizontal axis are the locations of the vortex cores (the wingtips).
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

|**Wing/Flow Type**|**Drag Components**|**Formula / Notation**|
|---|---|---|
|**Infinite Wing (2D)**|Skin Friction + Pressure|$C_d = \text{Profile Drag}$|
|**Subsonic Finite Wing**|Profile Drag + Induced Drag|$D_{total} = D_f + D_p + D_i$|
|**Supersonic Finite Wing**|Profile + Induced + **Wave Drag**|Sum of all four components|

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
## 