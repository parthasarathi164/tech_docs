>date created: 21-02-2026, Saturday
>**class 1 - 11**

>**Disclaimer:** This notes covers only the topics I consider most important and does not include all the content from the PPT.

# Aircraft Hydraulics and Pneumatics

## Aircraft Hydraulic System Components

- **Primary Sources of Mechanical Energy**: These include the aeroengine, Auxiliary Power Unit (APU), or Ram Air Turbine (RAT).
    
- **Reservoir**: A component used to store the hydraulic fluid.
    
- **Hydraulic Pumps**: These are responsible for generating the required flow within the system.
    
- **Accumulator**: A device that provides a means of storing hydraulic energy.
    
- **Hydraulic Fluid & Filters**: These work together to maintain clean hydraulic fluid.
    
- **Mechanism for Hydraulic Oil Cooling**: A dedicated system to dissipate heat generated during operation.
    
- **Multiple Redundant Distribution System**: A network consisting of pipes, valves, and shut-off cocks to ensure reliability.
    
- **Means of Exercising Demand**: Components such as actuators, motors, and pumps that perform work.
    
- **Pressure and Temperature Sensors**: Instrumentation that provides critical indications and warnings for system health.
    
![[Pasted image 20260221130137.png]]

---

## Hydraulic Reservoir

![[Pasted image 20260210210300.png]]

This is a hydraulic **reservoir** with quantity‑sensing and protection circuits.

- The main tank (pink) stores fluid; suction line feeds the pump, and the pressure/return lines circulate fluid through the system.
- A nitrogen‑pressurized space (orange) maintains positive pressure on the fluid so the pump never cavitates.
- PRV (pressure relief valve) sends excess pressure to the drain line; NRV (non‑return valve) controls flow in the return line.
- Float or piston–linked micro‑switches give “below 1 litre” and “below/above 4 litre” electrical signals, which can operate the isolation valve and cockpit quantity lights to protect the system from low fluid.

---

## Positive and Non-Positive Displacement Pumps

In fluid mechanics, pumps are generally categorized into two main types based on how they move fluid: **Positive Displacement** and **Non-Positive Displacement** (Dynamic).

---

### Positive Displacement (PD) Pumps

These pumps move fluid by trapping a fixed amount of it and forcing (displacing) that volume into the discharge pipe. They provide a constant flow at a fixed speed, regardless of the pressure against them.

- **Mechanism:** Uses expanding and contracting cavities (reciprocating or rotating).
    
- **Flow Rate:** Constant flow; the volume remains the same even if the system pressure increases.
    
- **Best For:** High-pressure applications, high-viscosity fluids (like oils or slurries), and precise metering.
    
- **Examples:** Piston pumps, gear pumps, vane pumps, and diaphragm pumps.
    

---

### Non-Positive Displacement (Dynamic) Pumps

These pumps use a rotating element (impeller) to add kinetic energy to the fluid, which is then converted into pressure energy. Unlike PD pumps, the flow rate changes significantly if the discharge pressure changes.

- **Mechanism:** Uses high-speed rotation to create velocity (centrifugal force).
    
- **Flow Rate:** Variable; if you restrict the outlet, the flow decreases, and the "slip" increases.
    
- **Best For:** High-volume flow, low-pressure applications, and low-viscosity fluids like water.
    
- **Examples:** Centrifugal pumps and axial flow pumps.
    

---

### Key Differences at a Glance

|**Feature**|**Positive Displacement (PD)**|**Non-Positive Displacement**|
|---|---|---|
|**Flow vs. Pressure**|Flow is independent of pressure.|Flow decreases as pressure increases.|
|**Fluid Viscosity**|Handles high viscosity well.|Efficiency drops with high viscosity.|
|**Efficiency**|Generally higher at high pressures.|Best at high flow rates.|
|**Priming**|Often self-priming.|Usually requires manual priming.|

---

## Gear Pump Formulas and Terms

### Volumetric Displacement ($V_D$)

$$V_D = \frac{\pi}{4}(D_o^2 - D_i^2)L$$

- **$V_D$**: Displacement volume of the pump ($\text{m}^3/\text{rev}$)
    
- **$D_o$**: Outside diameter of gear teeth ($\text{m}$)
    
- **$D_i$**: Inside diameter of gear teeth ($\text{m}$)
    
- **$L$**: Width of gear teeth ($\text{m}$)
    

---

### Theoretical Flow Rate ($Q_T$)

$$Q_T = V_D \times N$$

- **$Q_T$**: Theoretical pump flow rate
    
- **$N$**: Speed of the pump ($\text{RPM}$)
    

---

### Volumetric Efficiency ($\eta$)

$$\eta = \frac{Q_A}{Q_T} \times 100$$

- **$\eta$**: Volumetric efficiency
    
- **$Q_A$**: Actual flow rate (typically less than $Q_T$ due to internal leakage/slippage)
    

---

## External/Internal Gear, Vane, and Piston Pumps

### External Gear Pumps

These consist of two meshing gears—a drive gear and an idler gear—housed in a close-fitting casing.

- **Mechanism**: Fluid is carried between the gear teeth and the housing from the inlet to the outlet; as teeth mesh at the outlet, fluid is forced out.
    
- **Characteristics**: Simple, high-pressure capable, but can be noisy.
    
![[Pasted image 20260221124306.png]]

### Internal Gear Pumps

These use a large outer internal gear and a smaller inner external gear.

- **Mechanism**: The gears are separated by a crescent-shaped seal; as they unmesh at the inlet, fluid is drawn in, carried through the crescent, and discharged as they remesh.
    
- **Characteristics**: Compact and quieter than external gear pumps, excellent for high-viscosity fluids.
    
![[Pasted image 20260221130316.png]]

### Vane Pumps

These feature a rotor with several sliding vanes mounted eccentrically within a cam ring.

- **Mechanism**: As the rotor turns, centrifugal force (or springs) pushes vanes against the housing, creating expanding and contracting chambers that move the fluid.
    
- **Characteristics**: Efficient and provides a very smooth, low-pulsation flow; often used in automotive power steering.
    
![[Pasted image 20260221130326.png]]

### Piston Pumps

These use reciprocating pistons within cylinders to move fluid.

- **Mechanism**: A drive shaft moves pistons back and forth; on the intake stroke, fluid enters the cylinder, and on the power stroke, it is forced out.
    
- **Characteristics**: Capable of the highest pressures and most precise flow control (metering) of all PD pumps.

![[Pasted image 20260221124459.png]]

---

## Hydraulic Accumulators and System Operation

### Hydraulic Accumulator

A hydraulic accumulator is a critical device in an aircraft system that provides a means of **storing hydraulic energy**. By holding pressurized fluid, it acts as a secondary power source during high-demand periods or as an emergency backup if the primary pump fails.

---

### System Diagram and Timing Chart Analysis

The provided schematic and timing chart illustrate how a storage device (accumulator) interacts with system pressure and loading valves:

- **Pressure Management**: Between points **A and B**, the loading valve ($V_2$) is closed, allowing the pump to charge the system and increase the pressure at point **P**.
    
- **System Loading**: At point **B**, the system reaches its peak pressure, and the loading valve ($V_2$) opens to divert pump flow, while a check valve ($V_3$) maintains the stored pressure.
    
- **Actuator Demand**: When the actuator valve ($V_1$) opens (points **C to D** and **E to F**), the stored energy in the accumulator is used to move the actuator, causing a temporary drop in pressure at point **P**.
    
- **Safety Redundancy**: A pressure regulator ($V_4$) is included for safety, though it does not typically operate during normal use.
    
---

## Hydro-Pneumatic Accumulators

### Bladder Type Accumulator

The **bladder type** features a flexible, balloon-like separator inside a pressure vessel. It is pre-charged with nitrogen gas, which acts as the compressible medium.

- **Functionality:** When hydraulic pressure exceeds the pre-charge pressure, fluid enters the "Liquid side," compressing the bladder. When system pressure drops, the bladder expands, forcing the fluid back out to maintain flow or pressure.
    
- **Key Components:** The **anti-extrusion poppet** at the bottom is critical; it closes the port if the bladder expands too far, preventing the rubber from being pinched or shredded by the fluid outlet.
    
- **Best For:** Fast-acting response and absorbing high-frequency pressure spikes (pulsation dampening).
    
![[Pasted image 20260221131319.png]]

---

### Piston Type Accumulator

The **piston type** uses a heavy-duty, sealed piston that slides within a machined cylinder to separate the gas and liquid phases.

- **Functionality:** As hydraulic fluid is forced into the cylinder, it pushes the piston toward the gas side, compressing the nitrogen. When the system requires energy, the compressed gas expands and drives the piston back, discharging the fluid.
    
- **Key Components:** High-quality **piston seals** are vital to prevent gas from leaking into the hydraulic fluid (gas ingestion) while maintaining low friction for smooth movement.
    
- **Best For:** Managing large volumes of fluid, extreme temperature ranges, and applications requiring very high pressure ratios.

---

## Hydraulic Cooling and Cleaning

### Cooling Systems

Aircraft hydraulic systems generate heat through friction and pressure drops. Excessive heat degrades seals and lowers fluid viscosity, so **Heat Exchangers** (coolers) are used to maintain optimal temperatures.

- **Air-Oil Coolers:** These use ram air or fan air to cool the fluid as it passes through a radiator-like core. These are common in transport aircraft during flight.
    
- **Fuel-Oil Heat Exchangers:** Often used to transfer hydraulic heat into the aircraft's fuel. This serves a dual purpose: it cools the hydraulic fluid and pre-warms the fuel for better combustion efficiency.
    
- **Case Drain Lines:** Small amounts of fluid are bled off from pumps (carrying heat from internal friction) and sent back through the cooling circuit before returning to the reservoir.
    
![[Pasted image 20260221131645.png]]

### Cleaning and Filtration

To prevent "silting" (the buildup of fine particles) and damage to precision components like servo-valves, the fluid must be constantly cleaned.

- **Micronic Filters:** These use disposable elements (often made of pleated cellulose or synthetic fiber) to trap contaminants as small as 1–5 microns.
    
- **Differential Pressure Indicators:** Most filters include a "clogging" button (pop-up pin) that triggers when the pressure drop across the filter is too high, signaling that the element needs replacement.
    
- **Magnetic Plugs:** Many systems include magnets in the reservoir or return lines to trap metallic wear particles from pumps and actuators, preventing them from circulating.
    
- **Bypass Valves:** In the event of a total filter blockage, a bypass valve ensures the system still receives fluid (albeit unfiltered) to prevent catastrophic pressure loss in critical flight controls.

---

## Hydraulic Fluid Characteristics

### Essential Roles

Hydraulic fluid is the **power transmission medium** in an aircraft. It must be nearly incompressible to ensure instantaneous control response.

- **Lubrication:** Minimizes wear on high-speed pump components.
    
- **Cooling:** Carries heat from actuators and pumps to heat exchangers.
    
- **Sealing:** Provides a fluid seal between precision-machined parts.
    

### Critical Properties

To be effective in aviation, the fluid must meet these specific standards:

- **High Viscosity Index:** Remains fluid at **-54°C** yet retains "body" at high engine temperatures.
    
- **Fire Resistance:** Modern fluids (like **Skydrol**) have high flash points to prevent ignition during leaks.
    
- **Chemical Stability:** Must not corrode metal lines or cause seal degradation (swelling/cracking).
    
- **Low Foaming:** Must release air rapidly to prevent "spongy" controls and cavitation in pumps.

---

## Hydraulic Control Valves

### Infinite and Finite Position Valves

Valves are categorized by how many distinct states they can occupy during operation.

- **Finite Position Valves:** Have a specific number of set positions (e.g., 2-position or 3-position). They are either fully open to a port or fully closed.
    
- **Infinite Position (Proportional) Valves:** Can be throttled to any position between fully open and fully closed. This allows for precise control of fluid flow rate and actuator speed.
    

### Directional Control Valve (DCV) Construction

The internal mechanism determines how the valve directs fluid flow.

- **Spool Valve:** Uses a cylindrical shaft (spool) that slides back and forth to open or block ports. It is the most common type due to its versatility in port configurations.
    ![[Pasted image 20260221133352.png]]
    
- **Poppet Valve:** Uses a ball, cone, or disc held against a seat to block flow. They provide a near-perfect seal with zero leakage, making them ideal for high-pressure holding applications.
![[Pasted image 20260221133335.png]]
    
- **Rotary Valve:** Uses a rotating disk or cylinder with internal passages to connect different ports. These are often used as low-pressure pilot controllers or for simple hand-operated tasks.
    ![[Pasted image 20260221133449.png]]

### DCV Configurations and Pilot Operation

DCVs are defined by the number of ports (ways) and the number of positions.

![[Pasted image 20260221133437.png]]
#### Standard Center Positions

For **4-way, 3-position valves**, the center (neutral) position determines fluid behavior when the valve is not actuated.

![[Pasted image 20260221133425.png]]

- **Closed Center:** All ports (P, T, A, B) are blocked, locking the actuator in place and maintaining system pressure.
    
- **Open Center:** Pump (P) connects to tank (T), while actuator ports (A, B) are blocked, unloading the pump to reduce heat.
    
- **Tandem Center:** Pump (P) flows to tank (T) while actuator ports (A, B) are blocked, allowing flow to subsequent valves in series.
    
- **Float Center:** Pump (P) is blocked, but actuator ports (A, B) connect to tank (T), allowing the actuator to move freely via external forces.
    
- **Regenerative Center:** Pump (P) connects to both actuator ports (A, B) simultaneously, while the tank (T) is blocked. This allows for high-speed cylinder extension by routing rod-end fluid back into the piston end.
    
- **Pilot-Operated Valves:** Use a small "pilot" fluid pressure to move a larger main spool. This allows a small solenoid or manual signal to control very high-flow, high-pressure systems that would otherwise require massive physical force to shift.
![[Pasted image 20260221133505.png]]

### Check Valves and Flow Control

These components manage the direction and speed of the hydraulic fluid.

- **Check Valve:** A "one-way" valve that allows fluid to flow in one direction but blocks it in the opposite direction.
    ![[Pasted image 20260221133538.png]]
    
- **Flow Control Valve with Check Valve:** Often called a **One-Way Flow Control** or **Speed Controller**.
    
    - In one direction, fluid is forced through a restricted orifice (metering the flow speed).
        
    - In the reverse direction, the fluid bypasses the restriction through a built-in check valve, allowing "free flow".
![[Pasted image 20260221133550.png]]

---

## Hydraulic Linear Actuators

Hydraulic linear actuators (cylinders) convert fluid pressure into linear mechanical force and motion. They are the "muscles" of the hydraulic system, providing high power density for tasks like moving flight control surfaces or landing gear.

### Types of Linear Actuators

- **Single-Acting:** Pressure is applied to only one side of the piston to extend it; an external force or internal spring retracts it.
    
- **Double-Acting:** Pressure can be applied to either side of the piston, allowing for powered extension and retraction.
    
- **Tandem:** Two or more cylinders are connected in series to multiply the force output while maintaining a small diameter.
    

### Actuator Mathematics

The performance of a linear actuator is governed by the relationship between pressure, area, and flow rate.

**1. Force Calculation**

The force ($F$) exerted by a cylinder depends on the fluid pressure ($P$) and the effective area ($A$) of the piston.

$$F = P \times A$$

- **Extension Force ($F_{ext}$):** Uses the full area of the piston.
    
- **Retraction Force ($F_{ret}$):** Uses the "annular area," which is the piston area minus the area of the rod ($A_{piston} - A_{rod}$).
    

**2. Speed and Velocity**

The speed ($v$) at which the actuator moves is determined by the flow rate ($Q$) and the area ($A$).

$$v = \frac{Q}{A}$$

- Because the annular area is smaller than the full piston area, a cylinder will typically **retract faster** than it extends for a given constant flow rate.
    

**3. Mechanical Power**

The mechanical power ($HP$ or $W$) output of the actuator can be calculated by the product of force and velocity.

$$Power = F \times v$$

---

## Hydraulic Valves

![[Pasted image 20260221134413.png]]

---
## Key Design Requirements of Hydraulic circuit

For any complex engineering system (particularly in aerospace), the primary design goals focus on balancing physical constraints with long-term efficiency:

- **Size & Weight:** Minimizing **weight** and **volume** to ensure maximum efficiency and ease of integration.
    
- **Cost Management:** Keeping the **initial acquisition cost** low.
    
- **Operational Excellence:** Ensuring **high reliability** for safety and **low maintenance** requirements to reduce long-term operating costs.
    

---

## Failure Modes and Critical Scenarios

Engineers must account for various ways a system can fail to ensure safety under extreme conditions.

### Principle Failure Modes

- **Single vs. Multiple:** Handling the failure of one component or the simultaneous failure of several.
    
- **Dormant Failures:** Identifying issues in emergency-only systems that may go unnoticed until they are needed.
    
- **Common Mode Failures:** Addressing single events that can knock out multiple redundant systems at once.
    

### Critical Failure Examples

- **Take-off Emergencies:** Rapidly retracting landing gear during an engine shutdown or deploying brakes/spoilers during a rejected take-off.
    
- **System Damage:** Managing the loss of multiple hydraulic systems caused by an engine rotor burst.
    
- **Total Power Loss:** Developing ways to land safely even if all engines fail and main hydraulic/electric power is lost.

---

## Aircraft Failure Criticality and Design Standards

|**Failure Criticality**|**Failure Characteristics**|**Probability**|**Design Standard**|**Example (Hydraulic Systems)**|
|---|---|---|---|---|
|**Minor**|Normal, Nuisance and/or possibly requiring emergency procedures|Reasonably probable|Not applicable|Single hydraulic system fails|
|**Major**|Reduction in safety margin, Increased crew work load, may result in injury|Remote|$P \leq 10^{-5}$|Two (out of 3) hydraulic systems fail|
|**Hazardous**|Extreme reduction in safety margin, Major damage, possible injury/death|Extremely|$P \leq 10^{-7}$|All sources fail, except RAT or APU (e.g., US1549)|
|**Catastrophic**|Loss of aircraft with multiple deaths|Extremely improbable|$P \leq 10^{-9}$|All hydraulic systems fail (e.g., UA232)|

---

## Functions of Hydraulic systems

![[Pasted image 20260221140138.png]]

---

## Dual Channel Hydraulic System

This architecture utilizes two independent hydraulic circuits (Top and Bottom) to ensure continuous operation of flight-critical components even if one circuit fails.

![[Pasted image 20260221175900.png]]

### System Overview & Redundancy

- **Independent Circuits:** Each channel has its own **Reservoir**, **Shut-Off Valve (SOV)**, and **Pump (P)** to generate pressure.
    
- **Power Transfer System (PTS):** This central assembly features a motor-pump link (M-P) that allows one system to mechanically pressurize the other without fluid mixing, providing a critical backup if one main pump fails.
    
- **Tandem Actuator:** Both channels provide pressure to a single **Tandem Actuator**, which can be controlled by either system to maintain flight control authority.

---

### Key Components

- **Accumulators:** These store pressurized fluid to provide a temporary supply during peak actuator demands and to dampen pressure surges.
    
- **Heat Exchangers:** These use fuel as a cooling medium to dissipate heat from the hydraulic fluid, maintaining safe operating temperatures.
    
- **Filtration & Flow Control:** **Filters** remove contaminants immediately after the pump, while **Non-Return Valves (NRV)** prevent backflow and ensure unidirectional fluid movement.
    
- **Pressure Monitoring:** Integrated **Actuator Demands** signals and status valves help the system manage fluid distribution based on pilot inputs.

---

## Hydraulic System Circuit Diagrams (No. 1 and No. 2)

### No. 1 Hydraulic System: Primary Flight & Utility

This system is the main power source for standard flight and utility operations.

- **Utility Services (Green):** Manages non-critical components like the **I.F.R. Probe**, **Normal Brakes**, **Landing Gear (U/C)**, and **Flaps & Slats**.
    
- **Flight Controls (Blue):** Powers critical surfaces including the **Spoiler**, **Tail Plane**, and **Rudder**.
    
- **Safety Mechanism:** The **Service Isolation Valve** preserves pressure for flight controls by cutting off the utility side during a leak.

![[Pasted image 20260221140912.png]]

---

### No. 2 Hydraulic System: Emergency & Redundancy

This system serves as a specialized backup to ensure safety during equipment failures.

- **Emergency Utilities (Green):** Focuses on backup landing functions such as **Emergency Brakes**, **Parking Brake**, and **Emergency Landing Gear**.
    
- **Dedicated Accumulators:** Uses an **Anti-Shimmy Accumulator** for nose wheel stability and a **Brake Accumulator** for stopping power if pumps fail.
    
- **Redundant Flight Controls (Blue):** Provides secondary power to the **Spoiler**, **Tail Plane**, and **Rudder**, often through artificial stability (A/STAB) actuators.

![[Pasted image 20260221140932.png]]

---

## Nose Wheel Steering Control Unit Logic

The system functions through a continuous cycle of input, calculation, and feedback:

![[Pasted image 20260221142602.png]]

### 1. Primary Pilot Inputs

The **Nose Wheel Steering Control Unit** receives three distinct signals to determine the desired steering angle:

- **Steering Handwheel Command:** Large-angle steering inputs for low-speed taxiing.
    
- **Rudder Pedal Command:** Small-angle steering inputs for high-speed takeoff and landing rolls.
    
- **Equivalent Nose Wheel Inclination ($\alpha$):** A geometric calculation that adjusts the steering requirements based on the aircraft's current configuration.
    

### 2. Signal Processing & Error Calculation

Inside the control unit, these inputs are summed and compared against the **Steering Feedback Signal** from the actual landing gear.

- **Summation:** The pilot commands are combined into a single steering target.
    
- **Comparison:** The system calculates the difference (error) between the commanded angle and the current angle.
    
- **Control Rate:** This error is processed to determine the appropriate "rate" or speed at which the steering must move to reach the target.
    

### 3. Physical Actuation

The processed **Steering Command** is sent to the **Steering Control Valves**, which regulate hydraulic pressure to the **Nose Landing Gear** actuators to physically turn the wheels.

---

## Aircraft Braking Systems: Components and Requirements

Modern aircraft utilize several methods to decelerate and maintain control during ground operations, following strict performance and safety requirements.

![[Pasted image 20260221181548.png]]

### Primary Braking Components

- **Disc Brakes:** Located in the landing gear, these are used to slow the wheels directly while the aircraft is on the ground.
    
- **Thrust Reversers:** These redirect engine thrust forward to provide significant deceleration during the landing roll.
    
- **Air Brakes:** Dedicated flight control surfaces that increase aerodynamic drag to slow the aircraft.
    
- **Drogue Parachutes:** Primarily used by military aircraft (like the B-52) and select older civilian aircraft or the Space Shuttle to provide high-drag deceleration.
    

---

### Operational Requirements

- **Effective Application:** Systems must stop the aircraft effectively without causing skidding, which can lead to tire bursts and localized wear.
    
- **Stationary Stability:** The braking system must keep the aircraft stationary against engine thrust and strong crosswinds.
    
- **Parking & Maintenance:** Provisions are required for parking and picketing, as well as holding the aircraft during high-power ground engine runs for performance checks.
    
- **Ground Control:** Brakes enable precise control during the entire cycle of taxiing, takeoff, landing, and towing.
    
- **Differential Braking:** Systems must allow for differential braking as an alternative steering method to the nose wheel power steering.

---

## Aircraft Tyre Construction and Classification

The design and construction of aircraft tyres are critical for managing the extreme forces experienced during takeoff and landing.

### Structural Zones

An aircraft tyre is composed of four primary functional areas:

![[Pasted image 20260221182951.png]]

- **The Crown:** This is the top section that makes direct contact with the runway and contains the tread pattern.
    
- **The Shoulder:** A transition zone where the tyre structure thins as it moves from the crown toward the sidewall.
    
- **The Sidewall:** Considered the weakest part of the tyre, this area is most vulnerable to external damage.
    
- **The Bead:** A high-strength rim that secures the tyre to the metallic wheel, ensuring an airtight seal.
    

---

### Key Defining Characteristics

Tyres are engineered with specific properties to ensure safety and longevity:

- **Ply Rating:** A measure of the tyre's strength; higher ratings indicate a more robust construction.
    
- **Tread Design:** Typically features a "ribbed" pattern to effectively channel water and provide a tough, high-grip surface.
    
- **Tubeless Design:** Modern tyres often lack an inner tube, using a vulcanized lining to reduce weight and run at lower temperatures.
    
- **Vulcanization:** A chemical process that bonds polymer chains, making the rubber more elastic and resistant to abrasion.
    

---

### Types of Build: Bias vs. Radial

The internal structure is generally classified by how the "plies" (layers) are arranged:

- **Bias (Cross-ply):** Layers are laid in pairs with cords set at **90°** to one another.
    
- **Radial:** Layers are laid from bead to bead, running perpendicular to the tyre's centerline.

![[Pasted image 20260221182924.png]]

---

## Ground Handling Hazards: Creep and Hydroplaning

In addition to structural design, pilots and engineers must manage physical phenomena that affect how tyres interact with the runway surface.

### Aircraft Tyre Creep

Creep refers to the physical **movement or rotation of the tyre on the wheel rim** over time.

- **Cause:** It is primarily caused by the extreme torque and high-stress loads experienced during landing and heavy braking.
    
- **Risk:** If the tyre "creeps" too far, it can shear off the inflation valve (in tubed tyres) or break the airtight seal at the bead, leading to a sudden loss of tyre pressure.
    
- **Monitoring:** Maintenance crews often paint **creep marks** (white or red lines) across both the tyre sidewall and the wheel rim to visually check if any shifting has occurred.

![[Pasted image 20260221184146.png]]

---

### Hydroplaning (Aquaplaning)

Hydroplaning occurs when a layer of water builds up between the tyre's contact area and the runway surface, causing a **total loss of friction and braking effectiveness**.

- **The Mechanism:** At high speeds, the tyre cannot expel water fast enough, leading it to "float" on a thin film of liquid.
    
- **Prevention via Design:** Modern aircraft use a **ribbed tread pattern**, which creates flexible channels to expel water away from the contact patch.
    
- **Prevention via Operation:** Effective braking systems and anti-skid logic are required to stop the aircraft without causing the tires to lock up, which would worsen the hydroplaning effect.

![[Pasted image 20260221184132.png]]

---
## Aircraft Braking System Layout

![[Pasted image 20260221185244.png]]

The system is designed with multiple layers of control to manage hydraulic pressure to each individual wheel:

- **Pilot Inputs:** Both the Captain and First Officer have dedicated pedals to command braking.
    
- **Parking Brake:** A dedicated "Pull & Turn" handle applies constant pressure to all brakes and closes the parking brake valve to secure the aircraft when stationary.
    
- **Hydraulic Supply:** A main "Brake Hydraulic Supply" line feeds into **Brake Control Valves**, which regulate the flow based on the mechanical or electrical signals from the pedals.
    
- **Brake Units:** These physical components (green blocks) apply the hydraulic force to the inner and outer wheels of each landing gear assembly.
    

---

## Anti-Skid System Operation

**Components of Anti-Skid System:**
- Wheel Speed transducer
- Anti-Skid Control Unit
- Electro-hydraulic System for Anti-Skid System

The **Anti-Skid System** is a critical safety feature that prevents wheel lock-up, similar to ABS in a car, to maintain steering control and prevent tire bursts.

- **Tachometers (Tacho):** Each wheel is equipped with a tachometer that monitors its individual rotational speed.
    
- **Control Units:** The **Anti-Skid Control** units receive speed data from the tachos. If a unit detects that a wheel is slowing down too rapidly compared to others (indicating a skid), it sends a signal to intervene.
    
- **Skid Control Valves:** These valves are located between the main control valve and the brake units. They provide **independent control for all wheels**, momentarily reducing hydraulic pressure to the skidding wheel to allow it to resume rotation before reapplying pressure.

---

## Aircraft Braking Modes and Redundancy

Modern aircraft incorporate sophisticated braking systems to ensure safety during all phases of ground operation, from landing to parking.

### Automatic Braking

- **Function:** Integrated with anti-skid systems, it automatically brings the aircraft to a halt after landing or during a rejected takeoff without pilot intervention.
    
- **Override:** The automatic system is instantly deactivated if the pilot manually applies the brakes.
    

### Emergency Braking

- **Alternate Sources:** Commercial aircraft are always equipped with an alternate hydraulic source for braking power.
    
- **Last Resort:** If all hydraulic pressure is lost, a dedicated **brake accumulator** can provide up to six additional brake applications.
    

### Parking Brakes

- **Operation:** Set via a lever, this system allows brake pressure to be applied and held indefinitely while stationary.
    
- **Priority:** Applying the parking brake overrides all other braking systems, including anti-skid and touch-down protection.

---

## Landing Gear Structural Components

![[Pasted image 20260221191105.png]]

The assembly is designed to absorb high-impact forces while maintaining directional stability:

- **Shock Strut (Inner & Outer Cylinders):** The main vertical member that telescopes to absorb landing impacts and support the aircraft's weight.
    
- **Trunnion:** The pivot point that attaches the landing gear to the aircraft fuselage or wing, allowing it to retract or extend.
    
- **Drag Strut:** A bracing member that stabilizes the gear against longitudinal (forward and aft) loads during taxiing and landing.
    
- **Upper and Lower Torque Links:** Hinged links that prevent the inner cylinder from rotating within the outer cylinder, ensuring the wheels remain correctly aligned.
    
- **Wheels:** The final interface with the ground, providing the platform for braking and movement.

---

## Pressure Measuring Instruments in Aircraft

Pressure measurement is divided into several categories based on the reference point used and the specific state of the fluid being measured.

### Fundamental Pressure Categories

- **Absolute Pressure:** Measured relative to a perfect vacuum (absolute zero pressure).
    
- **Gauge Pressure:** Measured relative to the local atmospheric pressure.
    
- **Differential Pressure:** The difference between two unknown pressures, which may include atmospheric or two distinct system pressures.
    
- **Compound Pressure:** Capable of measuring both positive and negative (vacuum) pressures relative to the atmosphere.
    

---

### Specialized Measurement Types

- **Hydrostatic Pressure:** Measures pressure based on the height of a fluid column; typically used for liquid levels in tanks.
    
- **Dynamic Pressure:** Measures fluctuations caused by moving fluids, such as pulsations or flow-induced changes.
    
- **Intelligent Pressure Measurement:** Uses smart sensors for remote monitoring with features like self-calibration and digital communication protocols (e.g., HART, Foundation Fieldbus).
    

---

### Pressure Sensing Technologies

- **Piezoelectric:** Uses crystals that generate an electric charge proportional to the applied force.
    
- **Strain Gauge:** Measures the physical deformation of a membrane or diaphragm under pressure.
    
- **Capacitive:** Detects pressure by measuring the change in electrical capacitance between two plates as they move closer or further apart.
    
- **Resonant:** Based on measuring the shift in frequency of a resonant element as pressure is applied.

---

### 1. Bourdon Tube Based Gauges

This is a mechanical sensing element consisting of a curved, flattened tube that is sealed at one end.

- **Mechanism:** When pressure is applied to the open end, the tube tends to straighten out.
    
- **Result:** This movement is linked to a gear and pointer mechanism to provide a visual reading on a dial.

![[Pasted image 20260221212259.png]]

### 2. Diaphragm & Bellows Based Gauges

These instruments use flexible metal membranes or capsules to detect pressure changes.

![[Pasted image 20260222093152.png]]

- **Diaphragm:** A thin, flexible disc that deflects when pressure is applied to one side.
    
- **Bellows:** A series of stacked diaphragms forming a "concertina" shape that expands or contracts longitudinally.
    
- **Usage:** Highly sensitive, these are often used for measuring lower pressure ranges, such as airspeed or altitude.
    

### 3. Solid-State Sensing Devices

Modern aircraft utilize electronic sensors that have no moving parts, increasing reliability and integration with digital cockpits.

![[Pasted image 20260222093033.png]]

![[Pasted image 20260222093000.png]]

- **Piezoelectric:** Uses crystals that generate an electric charge when physically compressed by pressure.
    
- **Strain Gauge:** Measures pressure by detecting the change in electrical resistance of a material as it deforms under pressure.
    
- **Capacitive:** Detects pressure by measuring the change in electrical capacitance between two plates as the distance between them changes.

---

>date: 22-02-2026, Sunday

## Basic Components of a Pneumatic System

Pneumatic systems use compressed air to transmit and control energy, consisting of several specialized components to process, store, and utilize that air.

![[Pasted image 20260222101316.png]]

### Core Components

- **Air Filters:** These remove contaminants from the air to protect sensitive downstream components.
    
- **Air Compressor:** This is the primary power source, generating compressed air through either diesel or electrical operation.
    
- **Air Cooler:** Because air temperature increases during compression, coolers are used to bring the temperature back down to safe operating levels.
    
- **Dryer/Separator:** This removes water vapor and moisture from the air to prevent corrosion and system freezing.
    
- **Receiver Tank:** This acts as a storage reservoir for the compressed air coming from the compressor, ensuring a steady supply for the system.
    
- **Control Valves:** These are used to regulate, monitor, and control the direction of air flow and system pressure.
    
- **Air Actuator:** These include air cylinders and motors that translate the compressed air's energy into the physical mechanical movement required by the system.

---

## Pneumatic Air Treatment and Service Units

Atmospheric air contains dust, smoke, and moisture that can cause internal wear and corrosion. To ensure the reliable operation of pneumatic systems, the compressed air must undergo a two-stage treatment process to remove these impurities.

![[Pasted image 20260222102405.png]]

### Primary Air Treatment

This initial stage cleans and prepares the air immediately after it enters the system:

- **Inlet Filtration:** A large-scale intake filter prevents large particles from entering the compressor.
    
- **Cooling and Drying:** Compressed air is naturally hot and humid; a cooler lowers the temperature while a dryer removes moisture.
    
- **Inline Filtration:** An additional filter removes any remaining fine contaminant particles before the air reaches the storage tank.
    

---

### Secondary Air Treatment: The Service Unit

After primary treatment, the air passes through a "Service Unit" for final preparation before reaching the actuators. This unit combines three individual functions:

- **Separator/Filter:** Performs a final cleaning of the air.
    
- **Pressure Regulator:** Maintains a constant, monitored pressure for the downstream load.
    
- **Lubricator:** Adds a fine mist of oil to the air to reduce friction in the moving parts of the pneumatic system.

---

## Aircraft Pneumatic Systems

The pneumatic system utilizes compressed air to transmit power, following a process of generation, treatment, and storage to ensure operational reliability.

### Air Compression

The compressor acts as the heart of the system, converting mechanical energy into potential energy by reducing air volume to increase pressure.

- **Classification:** Compressors are categorized as **Positive Displacement** (such as Piston or Screw types) or **Dynamic Displacement** (like Axial or Centrifugal).
    
- **Piston Operation:** Common in aircraft, these range from **Single Acting** (one air pulse per stroke) to **Double Acting** (two pulses per stroke), with the latter reaching pressures above 30 bar and reducing air pulsation.

![[Pasted image 20260222112544.png]]
    
- **Selection Factors:** Units are chosen based on their delivery volume and the specific operating pressure required by the aircraft systems.
    

### Storage and Regulation

Compressed air is housed in an **Air Receiver Tank** to provide a steady, continuous supply.

![[Pasted image 20260222112613.png]]

- **Smoothing Flow:** The tank acts as a buffer to even out pulsations from the compressor, ensuring a stable pressure level.
    
- **Environmental Control:** Its large surface area helps dissipate heat, causing moisture to condense so it can be removed via a **water drain**.
    
- **Safety & Monitoring:** Tanks are equipped with **safety relief valves** to prevent over-pressurization, along with **pressure gauges** and **thermometers** for constant monitoring.
    

### Air Treatment

Before the air can be used, it must be cleaned and cooled to protect sensitive system components.

- **Filtration:** **Inlet filters** remove dust and particles; these include **Dry Filters** (disposable) and **Wet Filters** (which use an oil bath to trap dirt).
    
- **Heat Management:** Because compression raises air temperature, **coolers** (air or water-cooled) act as heat exchangers to lower the temperature.
    
- **Condensation:** The cooling process helps turn water vapor into liquid, further drying the air to prevent internal system corrosion.

---

## Pneumatic System Components

The following specialized components are used to treat and utilize compressed air within a pneumatic system:

![[Pasted image 20260222121858.png]]

### Lubricator

As a final step in air preparation, the lubricator adds a fine mist of oil to the compressed air.

- **Function:** It reduces friction and wear between the moving parts of the pneumatic actuators and valves.
    
- **Mechanism:** Air flow through the unit draws oil from a reservoir via a **siphon tube**, which is then atomized into **oil drops** and distributed as a mist throughout the system.
    

### Relief Valve

A relief valve acts as a critical safety device to prevent system damage from over-pressurization.

- **Operation:** It remains closed under normal conditions by a **pressure setting spring**.
    
- **Safety Action:** If the **source pressure** exceeds the spring's preset limit, the valve opens to **exhaust** the excess air until safe pressure is restored.
    

### Pneumatic Actuators

Actuators translate the potential energy of compressed air into physical mechanical movement, typically in a linear direction.

- **Single Acting Actuator:**
    
    - **Mechanism:** Compressed air is applied to only one side of the **piston** to extend the **piston rod**.
        
    - **Return:** Once the air pressure is removed, an internal **spring** automatically retracts the piston back to its original position.
        
- **Double Acting Actuator:**
    
    - **Mechanism:** This design features two ports: an **extend port** and a **retract port**.
        
    - **Action:** Compressed air is applied to one side to push the piston out and then to the opposite side to pull it back in, allowing for controlled, high-force movement in both directions.

---

## Pneumatic Circuit Symbols and Functions

Pneumatic symbols provide a standardized way to represent the function and flow of air through various control components.

### Directional Control Valves (3/2 and 5/2)

These symbols are represented by squares called "ports," where the number of squares indicates the number of positions and the numbers indicate ports/ways.

![[Pasted image 20260222122644.png]]

- **3/2 Valve:** Consists of **3 ports and 2 positions**. It is typically used to control single-acting cylinders, where one port is the inlet, one is the outlet to the actuator, and the third is the exhaust.
    
- **5/2 Valve:** Features **5 ports and 2 positions**. This is the standard valve for controlling double-acting cylinders, providing two ports for supply/exhaust to alternate the piston movement.
    

---

### Control and Safety Valves

- **Flow Control Valve:** This symbol usually depicts a restriction (throttle) and is used to regulate the speed of an actuator by limiting the volume of air passing through.

![[Pasted image 20260222122742.png]]
    
- **Non-Return Valve (NRV):** Represented by a ball in a seat, it allows air to flow in only **one direction** and blocks it in the opposite direction to prevent back-pressurization.

![[Pasted image 20260222122726.png]]
    
- **Shuttle Valve (OR Gate):** This valve has two inlets and one outlet. It allows the output to be pressurized if **either** of the two input signals is active.

![[Pasted image 20260222122758.png]]

---

### Memory Function

The memory function in pneumatics refers to the ability of a system to "remember" its last commanded state even after the initial signal is removed.

![[Pasted image 20260222122822.png]]

- **Operation:** This is typically achieved using a **double-pilot operated 5/2 directional valve**.
    
- **Function:** When a momentary pulse of air hits one side, the valve shifts and **stays in that position** until a pulse is received from the opposite side.

---

