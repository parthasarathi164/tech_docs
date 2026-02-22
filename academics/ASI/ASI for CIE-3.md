## aircraft fuel system

![[Pasted image 20260111115035.png]]

### 1. Functional Components (Legend)

Based on the provided diagram, here are the critical components:

- **Booster/Transfer Pumps (P):** Electrically driven pumps that provide pressurized fuel flow to the engines and move fuel between tanks.
- **Fuel Shut-off Valves:** Used to isolate engines or sections of the fuel manifold during emergencies or maintenance.
- **Cross-Feed Valves:** Allow fuel from any tank to be fed to any engine, ensuring engine operation if a specific tank pump fails and aiding in lateral balance.
- **Jettison Valves (J) & Gallery:** System used to rapidly dump fuel overboard in emergencies to reach the Maximum Landing Weight (MLW).
- **Refuel Valves (R) & Connection:** Entry points for ground refueling, directing fuel into the respective tanks via the refueling gallery.
- **Vent System:** Includes float-operated valves and surge tanks to equalize pressure and prevent tank rupture or collapse during altitude changes.
---
### 2. System Sub-Sections

- **Storage (Tanks):** The system uses multiple tanks including a **Centre Tank**, numbered wing tanks (e.g., **Tank No. 3, 4, 4A**), and a **Stabilizer Tank** in the tail for longitudinal trim control.
- **Engine Feed:** Fuel is pumped from the wing tanks directly to the engines (e.g., **No. 3 and No. 4 Engines**) through dedicated shut-off valves.
- **Transfer & Management:** The **Refuel & Jettison Gallery** acts as a common manifold. The **Inter-Engine Valve** and **Cross-Feed Valves** provide redundancy and management of fuel distribution.
---
### Key Exam Points for 10 Marks:

1. **Redundancy:** Mention how cross-feed valves allow any engine to run off any tank.
2. **Safety:** Detail the Jettison system (for weight reduction) and the Vent system (for pressure equalization).
3. **Trim:** Explain that the Stabilizer tank is used not just for storage, but for adjusting the aircraft's Center of Gravity (CG).
4. **Flow Direction:** Note that fuel typically flows from the tanks, through booster pumps, through shut-off valves, and finally to the engine high-pressure pumps.
---
## fuel tank inerting system

![[Pasted image 20260111115225.png]]

### **On-Board Inert Gas Generation System (OBIGGS)**

The OBIGGS is a critical safety system designed to prevent fuel tank explosions by managing the atmosphere in the tank's "ullage" (the empty space above the liquid fuel).

- **Primary Purpose:** The system's goal is to replace combustible air with **Nitrogen Enriched Air (NEA)** to keep oxygen levels below the threshold required for combustion (typically 9-12%).
- **Air Source and Conditioning:** High-pressure **Bleed Air** is tapped from the engines. It passes through a **Control & Shut-off Valve (SOV)** into a **Heat Exchanger** where it is cooled (aided by a fan) and then filtered to remove contaminants.
- **Air Separation Modules (ASM):** The conditioned air enters the ASMs, which contain hollow-fiber membranes. These modules separate the air into two streams based on molecular size and permeability.
- **Gas Distribution:**
    - **NEA (Nitrogen Enriched Air):** The nitrogen-heavy stream is directed through control valves and an oxygen sensor into the **Fuel Tanks** to maintain an inert environment.
    - **OEA (Oxygen Enriched Air):** The oxygen-rich byproduct is collected in a manifold and exhausted **Overboard**.
- **Monitoring and Control:** A **Control Unit** monitors the **Oxygen Sensor** and manages the **Bypass Valve** and **Control Valves** to ensure the NEA quality and temperature remain within safe operating limits.
---
## two types of air to air refueling

### 1. Probe & Drogue Technique

- **Mechanism:** The tanker extends a flexible hose ending in a funnel-shaped **"basket" (drogue)**. The recipient aircraft has a rigid **probe**.
- **Operation:** The **recipient pilot** is responsible for maneuvering and inserting the probe into the basket.
- **Flow Rate:** Approximately **2,500 kg/minute**.
- **Key Advantage:** A single tanker can refuel up to **three aircraft simultaneously** (using one center and two wing hoses).
- **Safety:** Considered less risky because the pilot can clearly see the probe and basket during the connection.

### 2. Boom/Receptacle Method

- **Mechanism:** The tanker uses a rigid, **telescopic boom** (located under the tail). The recipient aircraft has a **receptacle** (opening) usually on its top surface.
- **Operation:** Controlled by a dedicated **Boom Operator** on the tanker. The recipient pilot just maintains a steady formation.
- **Flow Rate:** Significantly faster at **3,500 kg/minute**.
- **Key Characteristic:** Higher risk/difficulty because the connection point is often **outside the recipient pilot’s field of vision** during the final stage.
---

![[Pasted image 20260112081304.png]]

### Quick Comparison Table

| **Feature**             | **Probe & Drogue**     | **Boom/Receptacle**   |
| ----------------------- | ---------------------- | --------------------- |
| **Recipient Hardware**  | Rigid Probe            | Receptacle (Inlet)    |
| **Tanker Hardware**     | Flexible Hose & Basket | Rigid Telescopic Boom |
| **Who Controls?**       | Recipient Pilot        | Tanker Boom Operator  |
| **Max Flow Rate**       | 2,500 kg/min           | 3,500 kg/min          |
| **Simultaneous Refuel** | Up to 3 aircraft       | 1 aircraft            |

**Exam Tip:** Remember that **Boom = Faster Flow**, while **Probe & Drogue = Multi-aircraft capability.**

## capacitive sensors for fuel measurement

![[Pasted image 20260111132907.png]]

### 1. Working Principle (1 Mark)

Capacitive sensors consist of two concentric tubes that act as electrodes. The capacitance of the probe changes as the level of fuel rises or falls because fuel and air have different **dielectric constants** (fuel is ~2.1, air is ~1.0).

### 2. Strategic Placement & Multi-Sensor Array (2 Marks)

- **Comprehensive Coverage:** A single sensor cannot accurately measure fuel in an irregularly shaped tank. Instead, a series of **6 to 12 probes** are distributed across the length and width of each tank.
- **Vertical Orientation:** Probes extend from the top to the bottom of the tank to capture the full range of fuel levels, from empty to full.

### 3. Compensating for Aircraft Attitude (2 Marks)

- **Attitude Error:** During maneuvers (climb, dive, or bank), fuel "sloshes" to one side of the tank. As shown in your provided diagram, as the aircraft **pitches** or **rolls**, the fuel surface shifts.
- **Averaging Logic:** By placing probes at various locations (forward, aft, left, right), the system can "average" the readings. If one probe reads lower due to pitch, another reads higher, allowing the **Fuel Quantity Computer** to calculate the true total volume.

### 4. The Compensator Probe (1 Mark)

A specialized **compensator probe** is typically located at the **lowest point** of the tank. Since the dielectric constant of fuel changes with temperature and fuel type (Jet A vs. Jet B), this probe remains fully submerged to provide a reference signal that allows the computer to convert volume into a precise **mass (kg/lbs)**.

---
### Summary for Exam:

- **Principle:** Change in capacitance due to fuel/air dielectric difference.
- **Placement:** Multiple probes distributed to cover irregular tank geometry.
- **Purpose:** To eliminate errors caused by **Pitch and Roll** and to calculate **Mass** instead of just volume.

## fuel system instrumentation

![[Pasted image 20260111135045.png]]

This diagram displays an **ECAM (Electronic Centralized Aircraft Monitor) Fuel Page**, which provides pilots with a real-time digital summary of the entire fuel system's status.

### Key Components & Indications (5 Marks)

- **Total Fuel Monitoring:** The system calculates and displays the **Total Fuel on Board (FOB)** (Item 2) and the specific amount of **Fuel Used** by each engine (Item 1).
- **Tank Quantities & Temperature:** It monitors individual fuel levels across the aircraft, including the **Outboard** (Item 9) and **Inboard** wing tanks (Item 10), as well as the **Center Tank** (Item 11). It also tracks the **Fuel Temperature** (Item 12) to ensure it stays within safe operating limits.
- **Valve Status:** The display uses symbols to show the positions of critical valves, such as the **Engine and APU Fuel Shut-off Valves** (Items 3, 4), the **Cross-feed Valve** (Item 5), and **Transfer Valves** (Item 8).
- **Pump Operation:** It provides a visual indication of whether the **Wing Tank Booster Pumps** (Item 6) and **Center Tank Booster Pumps** (Item 7) are currently switched on or off.
- **System Logic:** The schematic layout allows pilots to quickly verify the flow of fuel from the tanks, through the pumps and valves, and finally to the engines or the Auxiliary Power Unit (APU).
---

## ultrasonic flow meter

![[Pasted image 20260111183941.png]]

### 1. Working Principle: Differential Transit Time (2 Marks)

- **The Method:** The system uses two ultrasonic transducers (A and B) positioned diagonally across a fuel pipe.
- **Time-of-Flight (ToF):** Transducer A sends an ultrasonic pulse to B (downstream), and B sends one back to A (upstream).
- **The Logic:** Sound travels faster when moving with the fuel flow and slower against it. The **time difference ($\Delta t$)** between these two pulses is directly proportional to the **velocity** of the fuel.

### 2. Microcontroller Role (MSP430FR604x) (1.5 Marks)

- **Signal Acquisition:** The **Ultrasonic Sensing Sub-system (USS)** manages the excitation of the transducers and uses a high-speed ADC to capture the reflected waveform (the signal envelope seen in the yellow box).
- **Processing (LEA):** The **Low-Energy Accelerator (LEA)** performs complex digital signal processing (like Cross-Correlation) independently of the CPU. This allows for extreme precision (accuracy of **<25 picoseconds**) while consuming very little power—ideal for battery-backed aircraft systems.

### 3. Volumetric to Mass Flow Conversion (1 Mark)

- **Density Factor:** Ultrasonic meters naturally measure **Volume Flow**. However, aircraft engines require **Mass Flow** (kg/hr) for accurate performance.
- **Compensation:** The system must account for fuel temperature and density changes. It uses the CPU to perform look-up table calculations based on the **Absolute Time of Flight**, which can infer the speed of sound and fluid properties without an external temperature sensor.

### 4. Advantages for Aircraft (1.5 Marks)

- **Non-Intrusive:** No moving parts (like mechanical turbine meters) means there is zero **pressure drop** and reduced risk of mechanical failure.
- **Reliability:** The system is resistant to **NVH (Noise, Vibration, and Harshness)** found in engine environments because it uses advanced algorithms to filter out unwanted interference.
- **Bi-directional:** It can accurately measure flow in both directions, which is useful for complex fuel transfer/jettison manifolds.
---
### Summary Table for Exam Prep

| **Component**     | **Function in the Metering System**                                    |
| ----------------- | ---------------------------------------------------------------------- |
| **Transducers**   | Convert electrical energy into ultrasonic pulses (133kHz–2.5MHz).      |
| **Pipe Geometry** | Provides the fixed cross-sectional area needed to calculate flow rate. |
| **USS Module**    | Handles pulse generation and high-speed signal capture.                |
| **LEA Block**     | Fast, low-power math processor for calculating the $\Delta t$.         |

## airbus a320 fuel system

![[Pasted image 20260111204940.png]]

### **Overview of the A320 Fuel System**

The A320 fuel system is a highly automated system designed for optimal weight distribution, wing loading relief, and redundancy. It consists of five primary fuel tanks integrated into the wings and center fuselage.

---
### **1. Tank Configuration & Storage (1.5 Marks)**

- **Total Tanks:** The system includes **one Center Tank (CTR TK)**, **two Inner Wing Tanks (INR TK)**, and **two Outer Wing Tanks (OUTR TK)**.
- **Capacity:** The total usable fuel is approximately **19,000 kg**.
- **Wing Bending Relief:** Fuel is kept in the outer tanks as long as possible to reduce structural loads on the wings during flight (wing bending and flutter relief).

### **2. Fuel Feeding & Usage Sequence (1.5 Marks)**

The system follows a specific automatic sequence to manage the aircraft's Center of Gravity (CG):

1. **Center Tank:** If fuel is present, the **Center Tank** is typically emptied first.
2. **Inner Wing Tanks:** Once the center tank is depleted, fuel is used from the **Inner Tanks**.
3. **Outer Tank Transfer:** When the inner tank fuel level drops to a low level (~750 kg), the **Outer Tank Transfer Valves (XFR VALVES)** automatically open to allow fuel to gravity-feed into the inner tanks.

### **3. Pumps and Delivery (1.5 Marks)**

- **Booster Pumps:** The inner wing tanks each contain **two electrical booster pumps** (Pump 1 & 2) for redundancy.
- **Jet Pumps (Transfer Logic):** As shown in the diagram, newer A320 models use **Jet Pumps** to transfer fuel from the center tank to the inner tanks using motive flow from the wing pumps.
- **Suction Valves:** If all pumps fail, **Suction Valves** allow the engines to be fed by gravity from the inner tanks (gravity feeding is not possible from the center tank).

### **4. System Valves & APU Feed (1.5 Marks)**

- **Cross-Feed (X-FEED) Valve:** A double-motored valve that allows both engines to be fed from any tank, essential for balancing fuel or in engine-out scenarios.
- **Low Pressure (LP) Valves:** These valves isolate the fuel supply to the engines or the **Auxiliary Power Unit (APU)** during a fire or shutdown.
- **APU Fuel Pump:** A dedicated pump provides fuel to the APU during startup if the main tank pumps are not operating.
---
### **Exam Summary Table**

|**Component**|**Function**|
|---|---|
|**XFR Valve**|Transfers fuel from Outer to Inner cells.|
|**Jet Pump**|Moves fuel from Center Tank to Inner Wing Tanks.|
|**X-Feed Valve**|Connects left and right fuel manifolds.|
|**LP Valve**|Emergency shut-off for engine or APU fuel.|

## aeroengine lubrication system

![[Pasted image 20260111205813.png]]
fig: rotating components where lube is required

![[Pasted image 20260111205935.png]]

### 1. Pressure Subsystem (The Supply)

This circuit provides a continuous flow of clean, cooled oil to the engine's critical moving parts.

- **Oil Tank:** Acts as the reservoir for the oil supply.
- **Pressure Pump:** A positive displacement pump that draws oil from the tank and delivers it under pressure to the system.
- **Pressure Filter:** Removes any fine contaminants from the oil before it reaches the bearings.
- **Distribution:** The pressurized oil is directed to the **Bearing Compartments**, the **Transfer Gearbox (TGB)**, and the **Accessory Gearbox (AGB)** to reduce friction and carry away heat.

### 2. Scavenge Subsystem (The Return)

Since this is a "dry-sump" system, oil must be actively pumped out of the bearing areas back to the tank.

- **Scavenge Pumps:** The diagram shows **5 Scavenge Pumps** (usually with a higher capacity than the pressure pump) that "suck" oil from the bearing sumps and gearboxes.
- **Scavenge Filter:** Traps any wear debris or carbon deposits picked up from the engine internals.
- **Fuel Cooled Oil Cooler (FCOC):** A heat exchanger where hot oil transfers its heat to the cold aircraft fuel. This simultaneously cools the oil and pre-heats the fuel for better combustion efficiency.

### 3. Venting and Pressurization Subsystem

This system manages internal pressures and ensures the oil remains inside the sumps.

- **Vent Lines:** These lines connect the bearing compartments and gearboxes to the oil tank to equalize pressure.
- **De-Oiler:** A centrifugal device that separates air from the oil-air mist before venting excess air overboard through the **Overboard Vent**. This prevents excessive oil loss.
- **Air Seals:** Though not explicitly drawn, the vent system works with air seals at the bearing compartments to ensure oil does not leak into the engine's gas path.
---
### Summary Table for Exam Prep

|**Component**|**Function**|
|---|---|
|**Pressure Pump**|Delivers oil to bearings and gearboxes.|
|**Scavenge Pumps**|Returns oil from sumps to the tank (prevents flooding).|
|**FCOC**|Uses fuel to cool the engine oil.|
|**De-Oiler**|Separates oil from air before venting overboard.|
|**Filters**|Ensure oil remains free of contaminants and debris.|

**Exam Tip:** Be sure to mention that the **Scavenge Pumps** always have a larger total capacity than the **Pressure Pump**. This ensures that the sumps remain dry, preventing oil from "churning" and overheating.

---

## aeroengine ignition system

### **Aero-Engine Ignition System Overview**

The ignition system in a gas turbine engine is responsible for providing the high-intensity spark required to ignite the fuel-air mixture during starting and to provide a "relight" capability during flight in case of an engine flameout.

#### **Core Components (3 Marks)**

The ignition system in passenger aircraft engines typically consists of two independent circuits for redundancy, each including:

- **Two Ignition Exciters:** These units receive a low-voltage electrical power supply and transform it into high-voltage electrical energy stored in capacitors.
- **Two Ignition Leads:** These are high-tension, shielded cables that transmit the high-voltage energy from the exciters to the igniter plugs.
- **Two Igniter Plugs:** Located in the combustion chamber, these plugs convert the high-voltage electrical energy into a high-intensity spark to ignite the fuel.

![[Pasted image 20260112074830.png]]
fig: cut section of an igniter plug

#### **Key Features & Operation (2 Marks)**

- **Redundancy:** Most systems are "dual systems," meaning there are two of each component (exciters, leads, and plugs) to ensure that if one half fails, the engine can still start or remain running.
- **Intermittent Duty:** Unlike a piston engine where the spark plugs fire continuously, aero-engine igniters are typically only used during the **start cycle** or during hazardous weather conditions (heavy rain/icing) to prevent flameout.
- **Positioning:** The igniter plugs are strategically positioned in the engine's combustion section (often at the 4 o'clock and 8 o'clock positions) to ensure reliable ignition of the fuel-air spray.
---

## fighter aircraft ignition system

![[Pasted image 20260112075332.png]]

This diagram illustrates a high-performance **Fighter Aircraft Ignition System** managed by a Full Authority Digital Engine Control (FADEC):

### 1. Primary Power Source: The Alternator (1 Mark)

- **Self-Sufficiency:** The system utilizes a dedicated engine-driven **Alternator** to provide independent electrical power.
- **Speed Sensing:** It features three independent windings: one for high-voltage ignition power, one for the **N2 Tachometer** (RPM monitoring), and one providing feedback to the **FADEC Power Supply**.

### 2. Digital Management: The FADEC (2 Marks)

The FADEC acts as the "brain" of the system, making automated decisions based on real-time engine data:

- **Start & Protection:** It automatically manages the start sequence and monitors for failures like a **Flameout** or low RPM (**N2 < 45%**).
- **Logic Gate:** Using an "OR" logic gate, if it detects either a flameout or a dangerously low speed, it immediately triggers the **Relay** to activate the ignition system for a relight.

### 3. The Ignition Exciter Units (2 Marks)

Fighter systems often use multiple circuits for different stages of flight:

- **Main Circuit:** Provides high-voltage energy to the **Main Igniter** for standard engine starting and operation.
- **Afterburner (AB) Circuit:** A specialized circuit that activates when the pilot selects **AB Logic** (thrust boost), sending energy to the **AB Igniter** to light the fuel spray in the exhaust.
- **Energy Storage:** These units contain capacitors that store energy and discharge it as high-intensity sparks.

### 4. Emergency Redundancy: Backup Circuit (1 Mark)

- **Fail-Safe:** There is a dedicated **Backup Exciter** and **B/U Main Igniter** that can be activated via a **Backup Power & Ignition Switch**.
- **Direct Control:** This allows the pilot to manually force ignition even if the FADEC or primary power supply fails, ensuring the engine can be restarted in critical combat situations.
---
### **Summary Table for Exam Prep**

| **Component**  | **Role in Fighter System**                                       |
| -------------- | ---------------------------------------------------------------- |
| **FADEC**      | Digital controller for automatic starting and flameout recovery. |
| **Alternator** | Provides dedicated, independent power and speed signals.         |
| **AB Circuit** | Specifically for igniting the Afterburner/Augmentor.             |
| **N2 Tach**    | Measures engine RPM to determine when ignition is needed.        |

---
## aeroengine starting system

### **Types of Aero Engine Starting Systems**

Starting an aircraft engine requires a significant amount of energy to rotate the compressor and turbine to a speed where the engine can sustain itself. The four main types include:

- **Electric Starting System:** Commonly used in smaller gas turbine engines and business jets. It utilizes a powerful electric motor (often a combined starter-generator) powered by batteries or an external Ground Power Unit (GPU) to crank the engine.
- **Cartridge Based Starting System:** Historically used in military aircraft, this is a self-contained system. A solid propellant cartridge is ignited to produce high-pressure gas, which spins a small turbine connected to the main engine's gearbox.
- **Air Supplied (Pneumatic) Starting System:** This is the most common system for large commercial jet engines. High-pressure air is taken from an Auxiliary Power Unit (APU), a ground air cart, or a running engine ("cross-bleed") to drive a pneumatic starter motor.

![[Pasted image 20260112080106.png]]

- **Gas Turbine Based Starting System:** Used in large military or specialized aircraft, this involves a small, dedicated gas turbine engine (Jet Fuel Starter) that is mechanically coupled to the main engine to provide the necessary cranking torque.

![[Pasted image 20260112080130.png]]

---
## air start system of an aeroengine

![[Pasted image 20260112080800.png]]

### **Gas Turbine Air Starter System**

This system uses a small, dedicated gas turbine (the Air Generator) to produce the high-pressure pneumatic energy required to crank the much larger main engines.

- **Primary Power Source (Air Generator):** The system begins with a small gas turbine engine called an **Air Generator**. It has its own fuel supply from **Fuel Tank F3**, its own **Igniters**, and is managed by a **Starter Control Unit**.
- **Pneumatic Energy Production:** Once the Air Generator is running, it produces high-pressure air. This air is directed through a manifold to the main engines (No. 1 and No. 2).
- **Engine Cranking (Air Starters):** Each main engine is equipped with a pneumatic **Air Starter** motor. When the **Supply Valves** are opened, the high-pressure air spins these starters, which in turn rotate the main engine compressors to starting speed.
- **Control and Safety Logic:** The **Starter Control Unit** monitors the process using **Speed Probe Signals** from the Air Generator and both main engines. It also monitors the **Oil Pressure Switch (S/W)** to ensure the system is lubricated before allowing the start to proceed.
- **Air Management Valves:** The system includes various valves to manage the airflow, such as the **Air Vent Valve** and **Discharge Valve**, which ensure that air pressure is regulated and safely bled off once the main engines reach self-sustaining speed.
---
## aeroengine fuel & control system

![[Pasted image 20260112081810.png]]

This diagram presents a **Simplified Engine Fuel System**, outlining the journey of fuel from the airframe tanks to the engine burners:

### 1. Main Engine Pumping Unit (1.5 Marks)

The system utilizes a two-stage pumping process to ensure reliable delivery at varying pressures:

- **Low Pressure (LP) Pump:** The first stage that draws fuel from the aircraft tanks and increases pressure enough to overcome system resistance.
- **Fuel/Oil Heat Exchanger (FOHE):** Before reaching the second pump, fuel passes through the FOHE, where it cools the engine oil while simultaneously warming the fuel to prevent ice crystal formation.
- **High Pressure (HP) Pump:** A gear-type pump that further increases pressure to the levels required for high-accuracy metering and fine atomization at the burners.

### 2. Servo Fuel & Actuation (1 Mark)

- **VSV Actuators:** A portion of the HP fuel is tapped off as "**Servo Fuel**" to power hydraulic actuators like the **Variable Stator Vanes (VSV)**.
- **Return Circuit:** Once used for mechanical work, the servo fuel is returned to the HP pump inlet via the **Servo Fuel Return** line.

### 3. Fuel Metering System (1.5 Marks)

This is the "intelligence" of the system, ensuring the engine receives exactly the right amount of fuel for the pilot's throttle setting:

- **FMV (Fuel Metering Valve):** Precisely controls the volume of fuel flow directed toward the burners.
- **Pressure Drop & Spill Valve:** Maintains a constant pressure across the FMV. Any excess fuel not required by the engine is "spilled" back to the HP pump inlet via the **Spill Fuel** line.
- **HP Fuel Shut-Off Valve:** Provides a positive means to stop fuel flow immediately during engine shutdown or emergency situations.

### 4. Final Delivery & Filtration (2 Marks)

- **Flow Meter:** Measures the actual mass of fuel passing to the engine to provide accurate "Fuel Flow" data to the cockpit.
- **HP Filter:** Acts as a final "last-chance" filter to trap any microscopic debris before the fuel enters the sensitive burner nozzles.
- **Burners:** The final destination where fuel is sprayed into the combustion chamber in a fine mist to be ignited.

### detailed fuel and control system - https://youtu.be/SKiavNTIIsQ

---
## spray nozzle systems

![[Pasted image 20260112082425.png]]

**Fuel spray nozzles** atomize fuel into patterns for efficient combustion and are located on the compressor discharge case.

- **Simplex Nozzle:** Features a single orifice. Fuel enters a **spin chamber** via tangential holes, creating a high-velocity swirl that exits as a fine mist.
- **Duplex Nozzle:** Uses two orifices—**Primary and Secondary**. It starts on the Primary only for ignition. At higher RPM (N1), a flow divider valve opens the Secondary for full-power fuel volume.
---
## afterburner

![[Pasted image 20260112083854.png]]

### **1. Operation & Pilot Interface (2 Marks)**

- **Throttle Lever Position (PLA):** Afterburner is activated only when the pilot moves the throttle lever past a specific "gate" or detent into the **AB range**.
- **PLA Signal:** This mechanical position is converted into an electrical signal (Power Lever Angle - PLA) and sent directly to the **FADEC/Engine Control Unit**.

### **2. Control Logic & Fuel Metering (2 Marks)**

- **FADEC Logic:** The FADEC processes the **AB Logic** signal. It determines if engine conditions (like RPM and temperature) are safe to support the massive increase in fuel flow.
- **Fuel Manifolding:** Unlike the main burners, AB fuel is sprayed through a separate manifold directly into the exhaust pipe. The control system uses a dedicated **AB fuel pump** and metering valve to manage this high-volume flow.

### **3. Ignition & Sensors (2 Marks)**

- **AB Ignition Circuit:** To light the spray in the high-velocity exhaust, the FADEC triggers a specialized **AB Exciter** and **AB Igniter**.
- **Safety Monitoring:** The system monitors the **N2 Tachometer** (engine speed) and internal pressures. If the engine speed drops below a safe threshold (e.g., **N2 < 45%**) or a flameout is detected, the control system will automatically cut AB fuel to prevent an engine stall or surge.
---
## variable exhaust nozzle (VEN)

![[Pasted image 20260112084229.png]]

### **Variable Exhaust Nozzle (VEN) System Overview**

The VEN system physically adjusts the exit area of the engine exhaust. This is necessary because when the afterburner is engaged, the temperature and volume of the exhaust gases increase drastically; if the nozzle area didn't expand, the back-pressure would cause the engine to stall.

### **1. System Components (2 Marks)**

The system consists of several key hardware elements:

- **VEN Power Unit (VPU):** The main hydraulic or pneumatic source that provides the force needed to move the nozzle segments.
- **VEN Actuators:** Usually three synchronized cylinders that push or pull an **Actuating Ring** to change the nozzle geometry.
- **VEN Position Transmitter:** A feedback sensor that tells the control unit the exact current position of the nozzle.
- **10-Micron Filter:** Ensures the hydraulic fluid remains free of tiny contaminants that could jam the sensitive actuators.

### **2. Control Logic & Input (2 Marks)**

The nozzle is not manually moved by the pilot but is managed by a Digital Engine Control (DEC) or FADEC:

- **Inputs:** The DEC calculates the required nozzle position based on the **Power Lever Angle (PLA)** (throttle position) and internal engine temperature signals, such as **$T_5$** (turbine discharge temperature).
- **Closed-Loop Control:** The DEC sends a signal to the VPU to move the actuators. It then uses the **VEN Position Transmitter** to verify that the nozzle reached the target area, adjusting in real-time to maintain engine stability.

### **3. Operational Purpose (2 Marks)**

- **Afterburner Engagement:** When the pilot selects afterburner, the DEC commands the VEN to **open (increase area)** to accommodate the expanding hot gases.
- **Thrust Optimization:** At subsonic vs. supersonic speeds, the nozzle area is modulated to ensure the pressure at the exit matches the ambient atmospheric pressure as closely as possible, maximizing thrust and fuel efficiency.
- **Cooling:** The system includes an **Oil Cooler** in the return manifold line to manage the heat generated by the high-frequency movements of the hydraulic power unit.
---
## Full Authority Digital Engine Control (FADEC)

![[Pasted image 20260112084834.png]]

### **1. Definition of FADEC**

**Full Authority Digital Engine Control (FADEC)** is a high-performance, dual-channel digital computer system that manages all aspects of aircraft engine performance. It is "Full Authority," meaning it has complete control over the engine without requiring manual pilot intervention for basic operations.

### **2. Major Components of the System**

The FADEC system integrates several specialized control units to manage complex engine geometries and fuel requirements:

- **FADEC Computer:** The central processing unit (often dual-channel, Channel A and B, for redundancy) that runs control laws and voting logic.
- **Fuel Metering Unit (FMU):** Precisely controls the flow of fuel to the main engine burners.
- **Afterburner Fuel Control Unit (ABCU):** Specifically manages the high-volume fuel flow required for the augmenter/afterburner.
- **Variable Geometry Controls:** Includes **Fan Variable Geometry (FVG)** and **Compressor Variable Geometry (CVG)** controls to optimize airflow and prevent stalls.
- **Variable Exhaust Nozzle (VEN) Control:** Coordinates the exhaust area opening, particularly during afterburner use.

### **3. Sensor Inputs and Data Processing**

The FADEC makes real-time decisions by processing data from a wide array of sensors:

- **Speed Sensors:** Monitors **Fan Speed** and **Core Speed** to manage engine thrust and limits.
- **Temperature & Pressure:** Uses **$T_5$ (Turbine Temperature)**, **$T_1$ (Inlet Temp)**, and **$P_{s3}$ (Compressor Discharge Pressure)** to calculate engine health and fuel schedules.
- **Pilot Input:** Receives the **Power Lever Angle (PLA)** signal from the cockpit throttle.
- **Flame Sensor:** Detects engine flameout to trigger automatic relight sequences.

### **4. System Control Logic and Redundancy**

- **Dual-Channel Architecture:** FADEC systems typically feature two independent channels (A and B). Each channel has its own sensors and actuators to ensure that a single failure does not result in loss of engine control.
- **Fault Detection:** The computer constantly performs "Cross Channel Data Link" checks to compare data between channels.
- **Closed-Loop Feedback:** For systems like the **Variable Exhaust Nozzle (VEN)**, the FADEC sends a command to an actuator and uses a **Position Transmitter (LVDT)** to verify the mechanical movement was successful.
- **Safety Interlocks:** The system uses logic gates (such as an "OR" gate) to trigger emergency actions, such as activating the ignition relay if it detects **N2 < 45%** or a **Flame Out**.
---
### **Summary Table**

| **Functional Block** | **Exam Key Point**                                                            |
| -------------------- | ----------------------------------------------------------------------------- |
| **Authority**        | "Full Authority" means no manual backup is required for standard operation.   |
| **Redundancy**       | Dual-channel design ensures fail-safe operation.                              |
| **Input**            | Integrates airframe data (1553B Digital) with engine-specific analog sensors. |
| **Output**           | Drives hydraulic/pneumatic actuators for VEN, CVG, and FVG.                   |

---
## engine sensors

- **Fan Inlet Air Temperature Transmitter**: Measures the temperature of the air entering the engine fan. This data helps the FADEC calculate the correct air density for fuel scheduling.
- **Fan Speed Transmitters**: These monitor the rotational speed of the engine's low-pressure fan section. This is a primary indicator of the thrust being produced by the engine.
- **Electrical Chip Detectors**: These sensors use a magnet to attract and detect metallic particles in the engine oil. An alert is triggered if metal "chips" are found, indicating internal mechanical wear or damage.
- **Compressor Inlet Temperature Transmitter**: Measures the air temperature at the entrance of the high-pressure compressor. It provides data used to adjust variable geometry vanes to prevent compressor stalls.
- **Core Speed Sensor**: Monitors the rotational speed of the engine's high-pressure core (N2). It is critical for managing ignition sequences and detecting engine flameouts.
- **Oil Pressure Transmitter**: Measures the pressure of the lubrication oil supplied to the engine bearings. Low pressure readings trigger a cockpit warning to prevent engine seizure.
- **Thermocouple Harness**: A series of sensors that measure high temperatures in the turbine section (T5). This data is used to ensure the engine does not exceed its structural heat limits.
![[Pasted image 20260112085523.png]]
- **Afterburner Flame Sensor**: Detects the presence of a flame in the augmenter or afterburner section. It ensures fuel is cut immediately if the flame goes out to prevent an explosion.
- **Position Transmitters**: These track the mechanical position of movable parts like exhaust nozzles or variable vanes. They provide feedback to the control unit to verify that commands were executed correctly.
---
## throttle system

### **1. Signal Transmission via RVDT (2 Marks)**

- **Measurement:** The physical position of the cockpit throttle lever is converted into an electrical signal using two **Rotary Variable Differential Transducers (RVDT)**.
- **Redundancy:** To ensure fail-safe operation, each of the two independent **FADEC channels** is hard-wired to its own RVDT. This allows each channel to independently determine the precise throttle lever position without relying on the other.

### **2. Integration with FADEC and Auto throttle (2 Marks)**

- **Decision Making:** The FADEC uses this **Power Lever Angle (PLA)** signal as a primary input to determine the required engine thrust.
- **Automated Control:** The throttle system is also linked to the **Auto throttle computer**, which can command **servo-actuators** to physically move the levers or override manual positions to maintain target airspeeds or Mach numbers.

### **3. Control Modes of Operation (2 Marks)**

The throttle lever operates through several distinct modes, allowing the FADEC to schedule the appropriate fuel flow and engine geometry for various flight phases:

- **Idle Settings:** Includes **Ground Idle** for taxiing and **Flight Idle** for descent.
- **Power Settings:** Includes **Part Power** for cruise and **Intermediate Rated Power** for standard high-thrust requirements.
- **Advanced Modes:** Includes **Afterburner** for combat or takeoff boosts (triggering the AB fuel manifold and igniters) and **Auto-throttle** for computerized flight path management.
---
## auto throttle system

![[Pasted image 20260112085659.png]]

- **Definition:** An automated system that controls engine thrust to maintain specific airspeeds or thrust settings, reducing pilot workload.
- **Key Components:** Consists of an **A/T Computer** (logic), **Servo-actuators** (to physically move thrust levers), and cockpit switches like **ARM** and **TOGA**.
- **Operational Modes:**
    - **Speed Mode:** Automatically adjusts fuel flow to maintain a target airspeed/Mach number.
    - **Thrust Mode:** Maintains fixed power settings for specific phases like Takeoff or Climb.
- **System Inputs:** Processes real-time data from the **Air Data Computer (ADC)**, **Inertial Reference System (IRS)**, and engine **N1 sensors** to calculate safe thrust limits.
---
## Gyroscopes

![[Pasted image 20260112090732.png]]

### 1. Definition of a Gyroscope (1 Mark)

A gyroscope is essentially a spinning wheel or rotor mounted in a frame (gimbals) so that it can rotate freely in one or more directions. In aircraft, gyros are the heart of instruments like the **Heading Indicator**, **Attitude Indicator**, and **Turn Coordinator**, providing a stable reference regardless of the aircraft's movement.

### 2. Mechanical Gyros (1 Mark)

![[Pasted image 20260112090506.png]]
Mechanical gyros consist of a heavy, balanced metallic rotor that is spun at very high speeds (often 10,000 to 24,000 RPM). They can be powered in two ways:

- **Pneumatic (Vacuum):** A vacuum system sucks air past buckets on the rotor to spin it.
- **Electric:** An internal electric motor spins the rotor, providing higher reliability at high altitudes.

### 3. Rigidity in Space (2 Marks)

Rigidity is the primary property that allows a gyro to act as a reference point.

- **The Principle:** According to Newton’s First Law, a spinning rotor tends to maintain its orientation in space. It resists any force that tries to tilt its axis of rotation.
- **Factors:** The amount of rigidity depends on the **mass** of the rotor, the **distribution of mass** (radius), and the **rotational speed**.
- **Aircraft Use:** This property is used in the **Attitude Indicator** to provide a stable "artificial horizon" while the aircraft pitches and rolls around it.

### 4. Precession (2 Marks)

Precession is the characteristic that describes how a gyro reacts to an external force.

- **The Principle:** When a force is applied to a spinning gyro, the resulting movement (deflection) does not occur at the point where the force was applied. Instead, the movement occurs **90° later** in the direction of rotation.
- **The Effect:** This can cause "drift" or errors in instruments over time due to friction or the Earth's rotation.
- **Aircraft Use:** This property is used in the **Turn Coordinator**. As the aircraft yawns or rolls, the force causes the gyro to precess, which moves the needle on the instrument to indicate the rate of turn.
---
## effects on gyroscopes

- **Drift**: This is the lateral (horizontal) deviation of the spin axis of a gyroscope from its original reference point. It is usually measured in degrees per hour and can be caused by friction or imbalances.
- **Wander**: This is a general term describing the movement of the gyro's spin axis away from its fixed position in space. It is the result of both external forces and the Earth's natural rotation.
- **Real Wander**: This occurs when actual mechanical imperfections, such as bearing friction or unbalanced rotors, cause the gyro to move. It is a physical error inherent to the instrument itself.
- **Apparent Wander**: This is not a mechanical failure but occurs because the gyro stays fixed in space while the Earth rotates underneath it. To an observer on the ground, it "appears" that the gyro is moving when it is actually the Earth turning.
---
## types of gyroscopes

### **By Operational Type**

- **Displacement Gyros:** These measure the angular orientation of an aircraft relative to a fixed reference point. They are used in instruments like the **Attitude Indicator** and **Heading Indicator** to track how far the plane has pitched, rolled, or turned.
- **Space Gyros:** A type of displacement gyro that maintains its orientation relative to a fixed point in space. It relies on the principle of **rigidity** to remain stable while the aircraft moves around it.
- **Tied Gyros:** These are space gyros with a controlling force (like a leveling system) that keeps the spin axis tied to a specific local reference, such as the Earth's center.
- **Earth Gyros:** A specialized tied gyro that uses gravity-sensing mechanisms to keep its spin axis aligned with the Earth's local vertical (gravity).
- **Rate Gyros:** These measure the **rate** of angular change (degrees per second) rather than the total displacement. They are the core component of the **Turn Coordinator**, helping pilots maintain standard rate turns.

### **By Construction Method**

- **Tuned Rotor Gyros:** The traditional "spinning disc" type used in training aircraft for basic flight instruments. They use a heavy, high-speed metallic rotor to provide physical stability.
- **Ring Laser Gyros (RLGs):** Modern solid-state sensors that measure rotation by comparing two light paths traveling in opposite directions around a glass prism. They offer much higher reliability and accuracy than mechanical rotors for airliners.
- **Fiber Optic Gyros (FOGs):** An advancement of the RLG principle that uses long coils of optical fiber to detect rotation via the Sagnac effect. These are highly accurate and are found in ultra-modern aircraft like the **Airbus A380**.

### **By Power Source**

- **Suction Gyros:** These are independent of electrical power but are prone to variable rotor RPM if filters are blocked by dust or moisture. They may also fail at high altitudes due to insufficient manifold pressure.
- **Air Driven Type:** An engine-driven vacuum pump sucks filtered air through a jet that blows onto "buckets" on the rotor's edge to make it spin. It works on the same principle as a water wheel.
- **Electric Gyros:** These are heavier and more expensive but achieve target RPM faster and maintain it more accurately. They have a higher moment of inertia compared to air-driven types.
---
## artificial horizon and turn & bank indicator

![[Pasted image 20260112092648.png]]
### **1. The Artificial Horizon (Attitude Indicator)**

The Artificial Horizon (AH) is a primary flight instrument that displays the aircraft's pitch and bank angles relative to the Earth's horizon. It is essential for maintaining control when external visual references are lost.

#### **Core Principles and Construction**

- **Gyro Type:** It uses an **Earth Gyro** (a type of tied gyro) where the spin axis is maintained vertically by gravity. The rotor typically spins at approximately **15,000 RPM**.
- **Gimbal System:** The gyro is mounted in an inner gimbal (pivoted on the lateral axis) and an outer gimbal (pivoted on the longitudinal axis). This allows the instrument case to move freely around the stabilized gyro.
- **Visual Display:** A miniature aircraft symbol (gull-wing) is fixed to the instrument case, while a **horizon bar** is linked to the gyro and remains stabilized parallel to the true horizon.

#### **Instrument Presentations**

- **Straight and Level:** The horizon bar and aircraft symbol are perfectly aligned in the center.
- **Pitch Up/Down:** When the aircraft pitches up, the outer gimbal rises relative to the gyro, causing the horizon bar to move **down** relative to the aircraft symbol. The reverse happens during a descent.
- **Roll:** As the aircraft banks, the aircraft symbol rotates with the case while the horizon bar remains earth-horizontal, allowing the pilot to read the bank angle against a printed scale.

#### **Limitations and Features**

- **Toppling:** If the aircraft exceeds specific limits (e.g., ±85° pitch in modern units), the gyro may "topple," leading to erratic indications until it re-erects.
- **Electric Advantages:** Electric versions offer greater rigidity and incorporate **fast erection systems** (torque motors and mercury switches) to quickly return the gyro to the vertical after maneuvers.

---

![[Pasted image 20260112092715.png]]
### **2. The Turn and Slip Indicator**

This instrument combines two separate measuring devices on a single face to help the pilot perform coordinated (balanced) turns.

#### **A. Rate of Turn Indicator (The Needle)**

- **Mechanism:** It utilizes a **Rate Gyro** with a horizontal spin axis and only one degree of freedom.
- **Operation:** When the aircraft yawns (turns), a primary torque is applied to the gyro frame. Because the gyro is constrained, it **precesses** (tilts) about its gimbal axis.
- **Spring Balancing:** A calibrated spring resists this precession. The amount the spring stretches is proportional to the rate of turn.
- **Calibration:** The needle indicates standard rates: **Rate 1** (3° per second) and **Rate 2** (6° per second).

#### **B. Slip Indicator (The Ball)**

- **Construction:** Known as a "ball-in-tube" inclinometer, it consists of a weighted ball in a curved glass tube filled with damping liquid.
- **Balanced Turn:** In a coordinated turn, the resultant of gravity and centrifugal force acts directly down the aircraft's vertical axis, keeping the ball centered between the two etched lines.
- **Unbalanced Turns:**
    - **Slipping:** Occurs when there is **too much bank** for the rate of turn; the ball moves toward the inside of the turn.
    - **Skidding:** Occurs when there is **insufficient bank** (too much centrifugal force); the ball is slung toward the outside of the turn.
---
### **Summary Table**

| **Feature**            | **Artificial Horizon**        | **Turn and Slip Indicator**      |
| ---------------------- | ----------------------------- | -------------------------------- |
| **Gyro Type**          | Earth Gyro (Tied to Vertical) | Rate Gyro (Horizontal Axis)      |
| **Measurement**        | Displacement (Pitch & Roll)   | Rate (Yaw) + Balance (Slip/Skid) |
| **Degrees of Freedom** | Two                           | One                              |
| **Key Principle**      | Rigidity in Space             | Precession                       |

---
## Micro-Electro-Mechanical Systems (MEMS)

### **1. Directional Gyro Indicator (DGI)**

![[Pasted image 20260112094026.png]]

**Overview and Construction (4 Marks)**

- **Purpose**: Also known as the Heading Indicator, it provides a stable directional reference in azimuth for maintaining accurate headings and executing precise turns.
- **Syncing**: It has no magnetic element and is not north-seeking; it must be synchronized initially with a magnetic compass and checked regularly due to gyro wander.
- **Gyro Type**: It uses a tied gyro with freedom of movement in three planes, but the rotor axis is maintained in the yawing plane of the aircraft (horizontal in level flight).
- **Limitations**: If the aircraft exceeds pitch or roll limits of 85°, the gyro will "topple" against its stops, causing the scale to spin rapidly.

**Significant Errors in DGI (6 Marks)**

- **Gimballing Errors**: Occur when bank is applied due to the geometry of the gimbal system; these disappear once level flight is resumed.
- **Random Wander (Real Wander)**: The actual change in the rotor axis direction in space, though rates are very low (a few degrees per hour for electric indicators).
- **Apparent Wander (Earth's Rotation)**: Caused by the Earth rotating under a rigid gyro; the maximum rate is 15°/hour at the poles and zero at the equator.
- **Transport Wander**: Apparent wander caused by the change of the aircraft's position on Earth.
- **Drift Calculation**: The apparent drift rate is calculated as $15 \times \sin(\text{latitude})$ degrees per hour.

---

### **2. MEMS Technology Fundamentals**

**Components and Definitions (4 Marks)**

- **Definition**: Micro-Electro-Mechanical Systems (MEMS) are miniaturized mechanical and electro-mechanical elements made using micro-fabrication techniques.
- **Dimensions**: Sizes vary from below one micron to several millimeters.
- **Core Components**: The four functional elements are Micro-Sensors, Micro-Actuators, Micro-electronics, and Micro-structures.
- **Transduction**: Micro-sensors typically convert measured mechanical signals (like pressure or temperature) into electrical signals.

---

### **3. MEMS Pressure Sensors**

**Working Principles (6 Marks)**

- **Mechanism**: These work on the principle of mechanical bending of a thin silicon diaphragm when contacted by air, gas, or liquid pressure.
- **Piezoresistive Type**: Uses tiny piezoresistors placed strategically on the diaphragm; the strains from bending change the resistance, which is measured via a Wheatstone bridge.
- **Capacitive Type**: Measures the change in capacitance as the gap between plate electrodes changes due to pressure.
- **Comparison**:
    - **Piezoresistive**: Smaller, linear I/O relationship, but highly temperature sensitive.
    - **Capacitive**: Bulkier and nonlinear, but suited for high-temperature applications and lower cost.

![[Pasted image 20260112093420.png]]
fig: capacitive type mems pressure sensor

![[Pasted image 20260112093230.png]]
fig: resistive type mems pressure sensor

---

### **4. Accelerometers and Gyroscopes**

**MEMS Accelerometers (4 Marks)**

![[Pasted image 20260112093829.png]]

- **Structure**: Consists of a proof mass (known reference mass) supported by a spring and a dashpot for damping.
- **Sensing**: Acceleration causes a displacement of the mass, which is typically measured as a change in capacitance between fixed sensing fingers and the moving mass.

**MEMS Gyroscopes and Coriolis Effect (6 Marks)**

- **Coriolis Effect**: A mass moving with velocity ($v$) in a system rotating at an angular rate ($\Omega$) experiences an induced Coriolis force ($F_c$) perpendicular to the direction of motion.
- **Formula**: $\vec{F}_c = 2m\vec{v} \times \vec{\Omega}$.
- **Operation**: The induced force causes a displacement of the internal proof mass, resulting in a change in capacitance that corresponds to a specific angular rotation rate.

---

### **5. Optical Gyroscopes**

**Ring Laser Gyro (RLG) (6 Marks)**

![[Pasted image 20260112093855.png]]

- **Principle**: Operates on the Sagnac Effect using a ring interferometer.
- **Operation**: Two counter-propagating laser beams travel in a closed circle; when the unit rotates, the wavelengths change (increase in direction of rotation, decrease in opposite).
- **Beat Frequency**: The frequency difference ($\Delta f$) is proportional to the rotation rate: $\Delta f = \frac{4A\omega}{\lambda_0}$.
- **Advantages**: Lightweight, compact, self-contained, and has no moving parts, which eliminates friction.

**Fibre Optic Gyro (FOG) (4 Marks)**

![[Pasted image 20260112093945.png]]

- **Sagnac Effect**: Like the RLG, it measures the time difference between clockwise (CW) and counter-clockwise (CCW) light paths in coils of optical fiber.
- **Phase Shift**: The rotation induces a phase shift ($\phi_c$) proportional to the number of turns ($N$) and area ($A$): $\phi_c = \frac{8\pi NA\omega}{c\lambda_0}$.
---

>**upto class 37 (i guess)**

