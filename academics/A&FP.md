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

## for CIE-3

>date: 13-01-2026, Tuesday

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
