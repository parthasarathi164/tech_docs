>date created: 22-02-2026, Sunday
>**class 12 - **

>**Disclaimer:** This notes covers only the topics I consider most important and does not include all the content from the PPT.

# Aircraft

## Aircraft Electrical System Design Criteria

Aircraft electrical systems prioritize efficiency, weight reduction, and safety through specific AC and DC design standards.

### AC System Design (Large/Complex Aircraft)

AC systems dominate in large aircraft because they handle high power with lightweight conductors.

- **Standardization:** Operates at **115/200 V, 3-phase, 400 Hz**.
    
- **Weight Savings:** High frequency (400 Hz) allows for much smaller, lighter generators and transformers.
    
- **Voltage Flexibility:** Transformers easily step voltage up or down with minimal loss, optimizing long-distance transmission.
    
- **Power Quality:** Uses **IDG** or **VSCF** units to maintain constant frequency and voltage within strict tolerances.
    
- **EMI Management:** Requires shielded cabling and standardized grounding to protect avionics from electromagnetic interference.
    

---

### DC System Design (Light Aircraft & Secondary Power)

DC systems are preferred for short-distance delivery and powering sensitive electronic circuits.

- **Voltage Levels:** Typically **28 V**, though advanced jets use **270 VDC** to reduce current and wiring weight.
    
- **Precise Regulation:** Requires high accuracy (±1 V) to prevent damage to delicate avionics.
    
- **Distance Limits:** High power loss ($I^2R$) in low-voltage DC necessitates thick, heavy cables for long runs, limiting its use to short distances.
    
- **Component Durability:** Relays and bus bars use silver alloys to handle high inrush currents and prevent electrical arcing.
    
- **Circuit Stability:** Features reverse polarity protection and dedicated converters to ensure steady voltage regardless of battery state.

---

## Aircraft Electrical System Components

Aircraft electrical architectures rely on a variety of specialized components to generate, convert, and distribute power across different flight conditions and emergency scenarios.

![[Pasted image 20260222131412.png]]

![[Pasted image 20260222131523.png]]

- **Engine-Driven Generator (IDG):** This is the primary source of AC power, typically rated at **115/200 V, 400 Hz** with an output of **90–120 kVA**.
    
- **APU Generator:** Serving as an auxiliary or backup power source, it provides the same **115/200 V, 400 Hz** output as the main generators, typically at **90 kVA**.
    
- **Emergency Generator:** A critical backup for emergency AC power, often driven by a **Ram Air Turbine (RAT)** or a hydraulic motor, producing **5 kVA**.
    
- **Static Inverter:** This device converts DC power from the aircraft's battery into **115 V, 400 Hz AC** power for essential standby systems.
    
- **Transformer Rectifier Unit (TRU):** Essential for converting AC supply into regulated **28 V DC** output for electronic and avionics systems.
    
- **Bus Bars:** These serve as the central hubs for power distribution, connecting various power sources to their respective electrical loads.
    
- **GCU / GAPCU:** The **Generator Control Unit** (or Ground and Auxiliary Power Control Unit) manages power quality, control, and protection.
    
- **Safety Devices:** A network of **breakers, relays, and fuses** ensures system-wide safety by isolating faults and preventing electrical overloads.

---

### Comparison of Electrical System Components

| **Component**                     | **Function**                 | **Typical Rating / Output**   | **Power Source or Type**   |
| --------------------------------- | ---------------------------- | ----------------------------- | -------------------------- |
| **Engine-driven generator (IDG)** | Main AC power generation     | 115/200 V, 400 Hz, 90–120 kVA | Engine                     |
| **APU generator**                 | Auxiliary / backup power     | 115/200 V, 400 Hz, 90 kVA     | APU                        |
| **Emergency generator**           | Emergency AC power supply    | 115/200 V, 400 Hz, 5 kVA      | RAT / hydraulic drive      |
| **Static inverter**               | Converts DC to AC            | 115 V, 400 Hz, 1 kVA          | Battery                    |
| **Transformer rectifier (TRU)**   | Converts AC to DC            | 28 V DC output                | AC supply                  |
| **Bus bars**                      | Power distribution           | Varies by bus                 | All sources                |
| **GCU / GAPCU**                   | Power control and protection | —                             | Electrical management unit |
| **Breakers, relays, fuses**       | Safety and isolation         | —                             | System-wide                |

---

## Aircraft AC Generators: Principles and Construction

An AC generator (alternator) is an electromagnetic machine that transforms mechanical energy into electrical energy using the principle of induction.

![[Pasted image 20260222133610.png]]

### Working Principle

The operation is governed by **Faraday’s Law of Electromagnetic Induction**.

- **Electromagnetic Induction:** As an armature coil rotates within a magnetic field, the magnetic flux through the coil changes, inducing an alternating electromotive force (EMF).
    
- **Fleming's Right Hand Rule:** This rule determines the direction of the induced current within the rotating coil.
    
- **Mathematical Relationship:** The induced EMF ($\epsilon$) is proportional to the rotational speed; if the speed doubles, the generated EMF also doubles.
    
- **Output:** The resulting current is alternating, following a sine wave pattern: $I = \epsilon_0 \sin \omega t / R$.
    

---

### Core Construction Components

![[Pasted image 20260222133636.png]]

The machine consists of four primary physical elements that work together to produce electricity.

- **Armature:** A coil (labeled ABCD) made of numerous turns of insulated copper wire wrapped around a soft iron core.
    
- **Field Magnets:** Powerful permanent magnets or electromagnets with cylindrical poles (North and South) that create a uniform magnetic field perpendicular to the coil's rotation axis.
    
- **Slip Rings:** Two brass terminals attached to the ends of the armature coil that rotate in tandem with it.
    
- **Brushes:** Stationary carbon blocks that maintain constant electrical contact with the rotating slip rings to deliver the output to an external load.

---

## Aircraft AC Generator Mathematical Formulas

The operation of an AC generator is governed by electromagnetic equations that relate rotational speed, magnetic flux, and the resulting electrical output.

### Induced Electromotive Force (EMF)

The instantaneous EMF ($\epsilon$) generated in a rotating coil is calculated using Faraday's Law:

$$\epsilon = NBA\omega \sin(\omega t)$$

- **$N$**: Number of turns in the armature coil.
    
- **$B_m$**: Maximum magnetic flux density (measured in $Wb/m^2$ or Tesla).
    
- **$A$**: Surface area of the coil in $m^2$.
    
- **$\omega$**: Angular velocity of the coil, where $\omega = 2\pi f$.
    
- **$f$**: Frequency of rotation in revolutions per second.
    

---

### Peak and Alternating Values

- **Maximum EMF ($\epsilon_0$):** The peak voltage occurs when the coil is at **90°** to the magnetic field ($\sin(90°) = 1$):
    
    $$\epsilon_0 = N B_m A \omega = N B_m A (2\pi f)$$
    
- **Induced Current ($I$):** The alternating current delivered to the load is determined by the resistance ($R$) of the circuit:
    
    $$I = \frac{\epsilon}{R} = \frac{\epsilon_0 \sin(\omega t)}{R}$$
    

---

### Key Relationships for Numericals

- **Rotational Speed Influence:** If the rotational speed of the armature is doubled, the **Induced EMF** also doubles.
    
- **Flux Angle:** The magnetic flux ($\Phi$) at any given time ($t$) is calculated as:
    
    $$\Phi = NB \cos(\omega t) A$$

---

## 3-Phase AC and DC Generators

Aircraft utilize different generator architectures depending on whether the requirement is for high-power distribution (AC) or battery charging and electronic systems (DC).

---

### 3-Phase AC Generator

![[Pasted image 20260222134229.png]]

The 3-phase AC generator is the primary power source for large aircraft, typically outputting **115/200 V at 400 Hz**.

- **Construction:**
    
    - **Stator:** Consists of three separate sets of insulated windings placed **120° apart** around the internal circumference.
        
    - **Rotor:** An electromagnet (field) that is supplied with DC current to create a rotating magnetic field.
        
- **Working Principle:**
    
    - As the rotor spins, its magnetic field cuts through the three stationary stator windings.
        
    - According to **Faraday's Law**, this induces three separate alternating voltages that are 120° out of phase with each other.
        
    - This provides a smooth, continuous flow of high power with less weight than a single-phase system.
        

---

### DC Generator

![[Pasted image 20260222134406.png]]

DC generators are used primarily in light aircraft or as secondary power sources for systems requiring **28 V DC**.

- **Construction:**
    
    - **Field Magnets:** Stationary magnets (North and South poles) that create a fixed magnetic field.
        
    - **Armature:** The rotating part containing the coil where the current is induced.
        
    - **Commutator:** A split ring that acts as a mechanical rectifier to convert internal AC to external DC.
        
![[Pasted image 20260222134441.png]]

- **Working Principle:**
    
    - As the armature rotates within the fixed magnetic field, an alternating EMF is induced in the coil.
        
    - The **Commutator** reverses the connection to the external circuit every half-turn just as the current changes direction.
        
    - This ensures the current flows in only **one direction** to the stationary brushes, providing a direct current output.

---

## Integrated Drive Generator (IDG) Working and Construction

The IDG is a specialized electrical component that integrates a transmission and a generator into a single unit, ensuring a constant frequency output despite varying engine speeds.

### Operating Principle/Working

- **Drive Mechanism:** The IDG is driven by the engine's High Pressure (HP) compressor stage through the accessory gearbox.
    
- **Speed Management:** While the input drive speed varies with the engine's power rating, the IDG converts this into a constant speed to provide a steady **115/200 V, 400 Hz** three-phase AC supply.
    
- **Control:** The overall operation and output quality are monitored and managed by the **Generator Control Unit (GCU)**.

![[Pasted image 20260222141213.png]]

### Integrated Drive Generator (IDG) Components

The IDG is composed of two main sections—the Constant Speed Drive (CSD) and the Generator—supported by thermal and control subsystems.

#### Constant Speed Drive (CSD) Section

The CSD acts as a mechanical transmission that regulates varying engine input into a constant output speed.

- **Input Shaft:** Connects the IDG directly to the engine's accessory gearbox to receive mechanical power.
    
- **Disconnect Clutch & Solenoid:** Allows the pilot or system to mechanically decouple the IDG from the engine in the event of a thermal or mechanical fault.
    
- **Differential Gear (Summing Gear Train):** A planetary gear system that adds or subtracts speed to the input shaft to maintain a precise output rpm.
    
- **Variable Hydraulic Unit (Pump):** A variable-displacement pump that provides high-pressure oil to the fixed hydraulic unit to adjust gear ratios.
    
- **Fixed Hydraulic Unit (Motor):** A fixed-displacement motor that converts hydraulic pressure from the pump into mechanical rotation for the summing gear.
    
- **Hydraulic Trim Unit:** Fine-tunes the hydraulic flow to ensure the output speed remains exactly within the required 400 Hz tolerance.
    
- **Mechanical Governor:** A sensing device that monitors output speed and adjusts the hydraulic units to compensate for engine RPM changes.

#### Generator & Support Sections

This section converts the stabilized mechanical rotation into electrical energy and manages system health.

- **Permanent Magnet Generator (PMG):** An internal generator that provides self-sustaining electrical power for the IDG's control and excitation circuits.
    
- **Main AC Generator:** The primary component that produces the three-phase, 115/200 V, 400 Hz electrical supply for the aircraft.
    
- **Oil Circulation System:** An internal pump-driven network that provides lubrication and cooling to all moving parts and hydraulic units.
    
- **IDG Oil Cooler:** A heat exchanger that uses aircraft fuel to dissipate heat from the IDG's circulating oil.
    
- **Generator Control Unit (GCU):** An external electronic unit that monitors the IDG's voltage, frequency, and overall health to protect the electrical system.
    
- **FADEC Interface:** Connects the IDG to the engine's digital control system to coordinate power generation with engine performance.

---

## Aircraft AC Alternator

![[Pasted image 20260222141717.png]]

![[Pasted image 20260222141710.png]]

An AC alternator is an electromagnetic machine designed to convert mechanical energy from the aircraft engine into high-voltage alternating electrical current.

### Purpose and Why It Is Used

- **Power Density:** AC alternators are used because they can generate large amounts of power with significantly less weight than equivalent DC systems.
    
- **Efficiency:** High-frequency AC (400 Hz) allows for the use of smaller, lighter transformers and motors throughout the aircraft.
    
- **Voltage Management:** The alternating nature of the current permits easy stepping up or down of voltage using transformers to minimize transmission losses over long distances.
    
- **Reliability:** Brushless AC alternators are highly reliable and require less maintenance than older DC generators.
    

---

### Core Construction

- **Rotor:** The rotating part driven by the engine that creates a moving magnetic field.
    
- **Stator (Armature):** Stationary coils where the alternating current is induced as the rotor's field passes them.
    
- **Field Magnets:** Permanent or electromagnets used to produce the required magnetic flux.
    
- **Exciter:** A smaller internal generator that provides the DC current needed to power the main rotor's electromagnets.
    

---

### Working Principle

- **Induction:** Based on Faraday's Law, spinning a magnetic field near stationary coils induces an electromotive force (EMF).
    
- **Speed/Output Relation:** The induced voltage is directly proportional to rotational speed; doubling the speed doubles the generated EMF.
    
- **Output Type:** It produces a 3-phase sine wave, typically standardized at 115/200 V and 400 Hz for aircraft systems.

---

## Aircraft Electrical Power Distribution Systems

![[Pasted image 20260222184743.png]]

![[Pasted image 20260222184811.png]]

![[Pasted image 20260222184824.png]]

Aircraft distribution systems are designed based on the size of the aircraft, the complexity of the system, and the primary type of power generation (AC or DC).

- **Bus Bar (Bus):** A central conductor that carries the total electrical load and distributes it to individual power users.
    
- **Bus Tie Contactors (BTC):** Electric solenoids used to interconnect two separate bus bars.
    
- **Generator Line Contactors (GLC):** Solenoids that connect the generators directly to the distribution buses.
    
- **Bus Power Control Units (BPCU):** The central control units that monitor the entire network and automatically reconfigure the BTCs and GLCs if a generator fails or a bus shorts to ground.
    
- **Primary Conversion Principles:** Systems either use **AC generation** with Transformer Rectifier Units (TRUs) to obtain DC, or **DC generation** with inverters to obtain AC.
    
- **Split-Bus System:** This is the standard configuration for the Airbus A321 and most modern twin-engine jets, where two power systems (GEN 1 and GEN 2) operate completely isolated from one another.
    
- **Independent Regulation:** A major advantage of the split-bus design is that generator frequencies and phase relationships do not need to be synchronized because the systems never connect during normal operation.
    
- **Redundancy Protocol:** In the event of a generator failure, the BPCU connects the remaining operational generator (or the APU) to both buses to maintain the electrical load.
    
- **Parallel System:** A configuration where all generators are synchronized and connected to a single common bus to share the load evenly.
    
- **Split-Parallel System:** A hybrid design that typically operates as a split system but can be paralleled together for increased efficiency or during specific failure modes.

---

## Variable Frequency AC Generation System

![[Pasted image 20260222190233.png]]

Variable Frequency (VF) AC generation systems represent an advanced electrical architecture where the generator output frequency varies directly with engine speed, typically ranging from **360 Hz to 800 Hz**.

- **Architecture:** The system utilizes main engine generators (Gen 1 and Gen 2) and Auxiliary Power Units (APUs) to feed power directly into high-voltage AC buses, such as **230V** and **115V**.
    
- **Power Conversion:** Specialized units like the **Auto-Transformer Rectifier Unit (ATRU)** and standard **AC/DC converters** are used to transform this variable frequency AC into a stable **270V DC** or other DC loads.
    
- **Load Management:** The system distributes power to various "VF AC Loads" and uses an **Auto-Transformer Unit (ATU)** to bridge different AC bus voltages.
    
- **Battery Integration:** A battery system is maintained via DC/DC conversion to ensure emergency power and system stability.

---

## AC Power Characteristics

Aircraft AC power systems must maintain specific electrical standards to ensure the stable operation of sensitive avionics and flight systems.

|**Characteristics**|**Limits**|
|---|---|
|**Nominal Voltage**|115 Volts (Phase)|
|**Operating Voltage Range**|108 to 118 Volts|
|**Voltage Unbalance**|3 Volts Max|
|**Voltage Phase Difference**|116° to 124°|
|**Waveform Distortion Factor**|0.05 Max|
|**Crest Factor**|1.31 to 1.51|
|**DC Component**|+0.10 to -0.10 Volts|
|**Nominal Frequency**|400 Hz|
|**Operating Frequency**|393 to 407 Hz|
|**Frequency Drift Rate**|15 Hz per minute Max|

---

## Crest Factor in AC Waveforms

![[Pasted image 20260222193049.png]]

The **Crest Factor (CF)** is a mathematical ratio used to evaluate the quality and peak intensity of a steady-state electrical signal.

- **Definition:** It is the ratio of the **Peak Value** of a waveform to its **RMS (Root Mean Square) Average Value**.
    
- **Purpose:** It characterizes the quality of a waveform and indicates if it contains significant power peaks.
    
- **Application:** It applies only to steady-state signals such as sine, square, saw, or triangle waves.
    
- **Measurement:** It is sometimes expressed in **decibels** to show the difference between peak and average levels.
    
- **Aircraft Standards:** For aircraft AC power, the Crest Factor must typically remain within the range of **1.31 to 1.51**.

---

## Pitot-Static Pressure Sensing

![[Pasted image 20260222194729.png]]

Aircraft use specialized probes known as "pressure heads" to sense external air pressure, which is essential for calculating airspeed, altitude, and Mach number.

### Pitot Heads and Total Pressure

The pitot head is designed to capture the total pressure acting on the aircraft during flight.

- **Design:** An open-ended tube is aligned parallel to the aircraft's longitudinal axis to face directly into the moving airstream.
    
- **Mechanism:** As air enters the tube and is brought to rest, it generates "dynamic pressure." This dynamic pressure combines with the ambient "static pressure" already in the tube to provide **Total (Pitot) Pressure**.
    
- **Application:** This pressure is sent to instruments like the Airspeed Indicator or an Air Data Computer (ADC).
    

---

### Static Heads and Static Pressure

The static head is designed to sense only the ambient atmospheric pressure surrounding the aircraft, independent of its forward motion.

- **Design:** This tube has a sealed forward end but features holes or slots cut into the sides.
    
- **Sensing:** Because these slots do not face into the airflow, they sense only **Static Pressure**.
    
- **Suction Effect:** During flight, a suction effect occurs, making the sensed static pressure slightly lower than the actual atmospheric pressure.
    
- **Combined Units:** In many systems, the static and pitot sources are combined into a single "pressure head," where a static tube surrounds the pitot tube with separate internal lines for each.

---

## Pitot-Static Sensing Probes

Probes are essential for sensing the external air pressures needed to calculate flight data.

- **Pitot Head:** Senses **Total Pressure** through an open-ended tube facing the airstream.
    
- **Static Head:** Senses **Ambient Pressure** via side slots, unaffected by forward motion.
    
- **Combined Probe:** Integrates both pitot and static lines into a single unit.
    
- **Placement:** Mounted on the nose or fuselage outside the boundary layer.
    
- **Safety:** Features anti-icing heaters and drain holes to ensure accurate readings.

---

## Air data probes

![[Pasted image 20260222195712.png]]

![[Pasted image 20260222195717.png]]

![[Pasted image 20260222195845.png]]

---

## Pitot-Static System Errors

![[Pasted image 20260222200143.png]]

Pressure sensing is prone to specific errors caused by the aircraft's physical placement and movement through the air.

- **Position Induced Error:** This occurs when the probe senses a static pressure that is slightly lower than actual atmospheric pressure due to its location on the fuselage.
    
- **Placement Requirement:** To minimize this, probes must be positioned outside the aircraft's boundary layer, often on the nose or a strut.
    
- **Maneuver Induced Error:** This happens when the aircraft’s attitude changes (like high-G turns or pitching), causing the airflow to no longer be parallel to the probe opening.
    
- **Alignment Necessity:** Because the opening must be parallel to the airflow in normal flight, any deviation during maneuvers creates pressure inaccuracies.

---

## Aircraft Probe Heaters

![[Pasted image 20260222200231.png]]

Probe heaters are critical safety components designed to ensure the continuous and accurate sensing of air pressure by preventing ice buildup during flight.

- **System Integration:** Heaters are installed on both standalone pitot probes and combined pitot-static units.
    
- **Operational Protocol:** It is standard procedure for pilots to switch heaters **ON** during pre-takeoff checks and **OFF** after landing.
    
- **Cockpit Safety:** Modern aircraft are equipped with alert systems to warn the crew if the probe heaters are not activated while in flight.
    
- **Instrument Connection:** The heated probes supply vital pressure data to the Airspeed Indicator (ASI), Vertical Speed Indicator (VSI), and Altimeter.

---

## Total Air Temperature (TAT) Probe

The Total Air Temperature (TAT) probe is a critical sensor that measures the air temperature including the kinetic heating effects of high-speed flight, providing essential data for flight management and engine control systems.

---

![[Pasted image 20260222201256.png]]

### Construction and Function

- **Airflow Path:** Ram air enters the probe and is forced through a specialized internal duct that separates moisture and debris from the sensing element.
    
- **Sensing Element:** Located centrally within the probe, it measures the temperature of the air that has been brought to rest (stagnated).
    
- **Heating Elements:** Integrated into the probe body to prevent ice accumulation, which would otherwise block the airflow and lead to incorrect readings.
    
- **Aspiration System:** Uses an ejector fitting and engine bleed air to draw a continuous flow of air over the sensing element, even when the aircraft is at low speeds or on the ground.
    
- **Function:** By measuring the air's temperature at rest, the system can calculate Static Air Temperature (SAT) and True Airspeed (TAS) for precise navigation.
    

---

### Errors and Solutions

- **Radiation Error:** Solar heating can artificially raise the probe temperature; this is overcome by using highly reflective internal shielding and a high-velocity internal airflow.
    
- **Self-Heating Error:** The probe's internal heaters can bleed heat into the sensor; this is overcome by the "aspirated" design that uses bleed air to constantly flush the cavity with fresh ambient air.
    
- **Kinetic/Friction Error:** High-speed friction creates heat that doesn't reflect ambient temperature; this is overcome by calculating the recovery factor to mathematically derive the true Static Air Temperature (SAT).
    
- **Moisture/Icing Error:** Water or ice on the sensor causes evaporative cooling or blockage; this is overcome by the probe's "inertial separation" design which diverts heavy particles away from the sensing element.

---

## Basic Six Flight Instruments

![[Pasted image 20260222201603.png]]

The "Basic Six" are the primary instruments required on all aircraft to assist the pilot in controlling altitude, airspeed, attitude, and direction.

- **Pressure Altimeter:** Measures the aircraft's altitude above a fixed pressure level.
    
- **Air Speed Indicator:** Displays the aircraft's speed relative to the surrounding air.
    
- **Turn and Bank Indicator:** Indicates the rate of turn and the coordination of the aircraft.
    
- **Magnetic Compass:** Provides the aircraft's heading relative to magnetic north.
    
- **Vertical Speed Indicator:** Shows the rate at which the aircraft is climbing or descending.
    
- **Artificial Horizon:** Displays the aircraft's pitch and roll attitude relative to the horizon.

---

## Pitot-Static System Summary

![[Pasted image 20260222202003.png]]

The system uses external air pressure to provide data for key flight instruments.

- **Sensing:** Captures **Ram Air** (pitot) and **Ambient Air** (static).
    
- **Instruments:** Feeds the **Airspeed Indicator**, **Vertical Speed Indicator**, and **Altimeter**.
    
- **Safety:** Features **Heaters** for de-icing and an **Alternate Static Source** for backup.
    
- **Maintenance:** A **Drain Hole** removes trapped moisture.

---

## Aviation Airspeed Types and Corrections

### 1. Indicated Airspeed (IAS)

This is the raw value shown on the cockpit instrument, representing the speed at which the aircraft "feels" the air.

- **Function:** It measures the difference between total pressure and static pressure.
    
- **Key Benefit:** Regardless of altitude or temperature, the aircraft will always stall at the same **IAS** for a specific configuration.
    
- **Formula:**
    
    $$IAS = \sqrt{\frac{2(P_{Total} - P_{Static})}{\rho_0}}$$
    
- **Terms:**
    
    - $P_{Total}$: Total pressure (Pitot pressure)
        
    - $P_{Static}$: Static pressure
        
    - $\rho_0$: Density of air in a Standard Atmosphere ($1.225 \text{ kg/m}^3$)
        

### 2. Calibrated Airspeed (CAS)

This is the IAS corrected for **instrument and positional errors** caused by the aircraft's geometry.

- **Formula:**
    
    $$CAS = a_0 \sqrt{5\left[ \left(\frac{q_c}{P_0} + 1\right)^{2/7} - 1 \right]}$$
    
- **Terms:**
    
    - $a_0$: Speed of sound at sea level ISA ($661.47 \text{ knots}$ or $340.29 \text{ m/s}$)
        
    - $q_c$: Impact pressure
        
    - $P_0$: Sea level pressure ($1013.25 \text{ hPa}$ or $\text{Pa}$)
        

### 3. Equivalent Airspeed (EAS)

This is CAS corrected for **compressibility effects**, which become significant as the aircraft flies faster and higher.

- **Formula:**
    
    $$EAS = a_0 M \sqrt{\frac{P_s}{P_0}}$$
    
- **Terms:**
    
    - $a_0$: Speed of sound at sea level
        
    - $M$: Mach number
        
    - $P_s$: Static pressure at altitude
        
    - $P_0$: Sea level pressure
        

### 4. True Airspeed (TAS)

TAS is the actual speed of the aircraft **relative to the air mass** it is moving through, accounting for density changes.

- **Formula 1:**
    
    $$TAS = EAS \sqrt{\frac{\rho_0}{\rho}}$$
    
- **Terms:**
    
    - $EAS$: Equivalent Airspeed
        
    - $\rho_0$: Sea level air density
        
    - $\rho$: Local air density at the current altitude
        
- **Formula 2:**
    
    $$TAS = M \cdot a$$
    
- **Terms:**
    
    - $M$: Mach number
        
    - $a$: Speed of sound at given Outside Air Temperature (OAT), calculated as $\sqrt{\gamma R T}$
        
    - $\gamma$: Ratio of specific heats ($1.4$ for dry air)
        
    - $R$: Gas constant for air ($287.053 \text{ J/kgK}$)
        
    - $T$: Outside Air Temperature in Kelvin
        

### 5. Ground Speed (GS)

This is the speed of the aircraft **relative to the ground below**, used for navigation and flight timing.

- **Formula:**
    
    $$GS = TAS \pm \text{Wind}$$
    
- **Terms:**
    
    - $TAS$: True Airspeed
        
    - $\text{Wind}$: The velocity of the wind (add for tailwind, subtract for headwind)

---

## Machmeter

### Need for a Machmeter

- **High-Speed Performance:** As aircraft approach the speed of sound, they encounter compressibility effects that change aerodynamic behavior.
    
- **Safety Limits:** Pilots must monitor the Mach number to avoid exceeding the Maximum Operating Mach Number ($M_{MO}$), which can cause structural damage or loss of control due to "Mach tuck".
    
- **Efficiency:** It allows pilots to maintain optimal cruise speeds at high altitudes where the speed of sound varies significantly with temperature.

---

![[Pasted image 20260222203452.png]]

### Operating Mechanism

A Machmeter is essentially an airspeed indicator that is automatically corrected for altitude. It works by measuring the ratio of impact pressure to static pressure using the following internal components shown in the diagram:

- **Air Speed Capsule:** This diaphragm expands or contracts based on the difference between **Pitot Pressure** (inside the capsule) and **Static Pressure** (outside the capsule in the case).
    
- **Altitude Capsule:** Because the speed of sound changes with altitude, this evacuated capsule expands as the aircraft climbs to higher, thinner air.
    
- **Ratio Arm & Main Shaft:** The expansion of the Air Speed Capsule moves the **Air Speed Link**, which rotates the **Main Shaft**.
    
- **Mechanical Correction (Pin and Spring):** As the Altitude Capsule expands, it adjusts the position of the **Ratio Arm** (moving it along the path indicated by arrows A-B-C-D). This changes the leverage or gear ratio applied to the pointer.
    
- **Pointer and Gearing:** The combined movement of the airspeed and altitude mechanisms is transmitted through the **Ranging Arm** and **Hair Spring** to the dial gears.
    
- **Result:** The final position of the **Pointer** indicates the current Mach number, which is the ratio of the aircraft's True Airspeed (TAS) to the local speed of sound ($a$).

---

## Altimeter and Altitude Corrections

![[Pasted image 20260222211021.png]]

### Operating Principle of an Altimeter

An altimeter is a pressure-actuated instrument that measures an aircraft's vertical distance by sensing changes in atmospheric pressure.

- **Static Pressure Source**: The instrument is connected to a static port which provides the ambient air pressure of the current flight level.
    
- **Aneroid Wafers**: The core contains a stack of sealed, evacuated aneroid wafers that expand as atmospheric pressure decreases (during a climb) and contract as it increases (during a descent).
    
- **Mechanical Linkage**: This movement is transmitted through a main shaft and a series of gears to the pointer and gearing on the display.
    
- **Display Pointers**: Most altimeters use three pointers: the long hand indicates 100 ft increments, the middle hand indicates 1,000 ft, and the shortest hand indicates 10,000 ft.
    
- **Crosshatch Flag**: A specific crosshatched area may appear on the dial when the aircraft is flying below 10,000 feet MSL.
    

---

### Correction for Non-Standard Pressure

Since atmospheric pressure varies with weather, the altimeter must be calibrated to a local reference point.

- **Altimeter Setting Window**: Also known as the Kollsman window, this small scale shows the barometric pressure setting the instrument is referenced to.
    
- **Barometric Scale Adjustment Knob**: Pilots rotate this knob to input the local altimeter setting provided by air traffic control.
    
- **Pressure Error Rule**: If flying from an area of high pressure to low pressure without resetting the altimeter, the aircraft will be lower than indicated.
    

### Correction for Non-Standard Temperature

Altimeters are calibrated based on the Standard Atmosphere, where temperature decreases at a fixed rate ($2^{\circ}\text{C}$ per 1,000 ft).

- **Cold Air Effect**: In air that is colder than standard, the air is denser and the pressure levels are "compressed." This causes the altimeter to indicate an altitude higher than the aircraft's actual height.
    
- **Hot Air Effect**: In air warmer than standard, pressure levels are "expanded," and the aircraft will actually be higher than the altitude shown on the instrument.
    
- **True Altitude**: To find the actual height above sea level in non-standard temperatures, pilots must calculate the True Altitude using a flight computer or specific performance charts.

---

## Vertical Speed Indicator

![[Pasted image 20260222211840.png]]

### Operating Principle

The Vertical Speed Indicator (VSI) is a pressure-actuated instrument that indicates whether an aircraft is climbing, descending, or in level flight by sensing the **rate of change** in atmospheric pressure.

- **Diaphragm:** The inside of the diaphragm receives **direct static pressure** from the static port.
    
- **Case Pressure:** The area outside the diaphragm (within the instrument case) receives static pressure through a **calibrated leak**, which restricts the flow of air.
    
- **Pressure Differential:** During a climb or descent, the pressure inside the diaphragm changes instantly, while the case pressure changes slowly due to the leak.
    
- **Mechanism:** This pressure difference causes the **diaphragm** to expand or contract, moving a mechanical linkage that rotates the pointer on the dial to show feet per minute.

---

## Aircraft Directional Sensors and RVDT

### Angle of Attack (AOA) Vanes

![[Pasted image 20260222212644.png]]

The AOA vane measures the angle between the aircraft's longitudinal axis and the oncoming relative wind.

- **Alignment**: The sensor uses a balanced, low-friction vane that rotates to align itself with the local airflow.
    
- **Feedback**: This rotation provides critical data to the flight control system for stall prevention and monitoring the aircraft's aerodynamic envelope.
    
- **Components**: A complete unit includes the vane, a protective case, and an electrical connector for data transmission.
    

---

### Angle of Sideslip (AOSS) Vanes

![[Pasted image 20260222212651.png]]

AOSS vanes measure the lateral angle between the aircraft's centerline and the relative wind.

- **Lateral Sensing**: Unlike AOA which measures vertical pitch angles, AOSS detects if the aircraft is skidding or slipping sideways through the air.
    
- **Efficiency**: The data is used to maintain coordinated flight, minimizing drag and improving fuel economy.
    
- **Stability**: It is essential for fly-by-wire systems to manage lateral-directional stability, especially during engine-out conditions.
    

---

### Rotary Variable Differential Transformer (RVDT)

![[Pasted image 20260222212710.png]]

An RVDT is an electromechanical transducer that converts the angular position of a sensor, like an AOA or AOSS vane, into a proportional electrical signal.

- **Non-Contact Design**: It operates using magnetic coupling between a primary coil and two secondary coils, meaning there is no physical contact or wear between the sensing elements.
    
- **Linear Output**: As the input shaft (connected to the vane) rotates, the RVDT produces an AC voltage output that varies linearly with the angle.
    
- **Reliability**: Due to their lack of brushes or wipers, RVDTs are highly durable and preferred for critical flight control applications.

---

## Nose Air Data Probe (NADP)

![[Pasted image 20260222220941.png]]

![[Pasted image 20260222221021.png]]

### General Function and Location

- The Nose Air Data Probe (NADP) is a specialized instrument located at the tip of the aircraft nose, as seen on the LCA.
    
- It is designed to sense multiple atmospheric parameters simultaneously through a series of integrated ports and holes.
    
- The probe features a pointed tip for the Total Pressure port and various side holes for sensing other pressures.
    

### Port Configuration and Parameters

- The NADP utilizes nine ports in total to measure four distinct flight parameters.
    
- One port is dedicated to sensing Total Pressure ($P_T$) at the very front of the probe.
    
- Four ports are used to sense Static Pressure ($P_S$).
    
- Two ports measure differential pressures ($P\alpha1$ and $P\alpha2$) that are proportional to the Angle of Attack (AOA).
    
    - These are located on the bottom and top sides of the probe respectively.
        
- Two ports measure differential beta pressures ($P\beta1$ and $P\beta2$) that are proportional to the Angle of Sideslip.
    
    - These are located on the right and left sides of the probe respectively.
        
- The probe also includes a Pitot drain hole on its bottom side to remove moisture.

---

## Side Air data probe

![[Pasted image 20260222221334.png]]

---

## De-Icing Current Sensing Unit (DCSU)

![[Pasted image 20260222221636.png]]

The **DCSU** is a critical system component designed to ensure the reliability of aircraft sensors in icing conditions by providing and monitoring heating currents for de-icing.

- **Heating and Monitoring**: It provides heating current to passive resistor heaters for de-icing sensing ports and monitors the status and current of all connected heaters.
    
- **Interfaces**: The unit is interfaced to air data probes and vanes on the primary side and to the **Air Data Computer (ADC)** on the secondary side via current transformers.
    
- **Sensing Path**: Current transformers are connected in a series path to sense the de-icing current for each heating element.
    
- **Connected Sensors**: It manages de-icing for the **NADP**, **SADP**, **AOA sensors** (vanes and cases), **AOSS sensor**, and the **TATP**.

---

## Functional Breakdown of the Air Data Computer (ADC) Architecture

![[Pasted image 20260222222103.png]]

- **Power Supply Module (Pink):** This section takes in external 28V DC power and processes it through a transient suppressor and EMI/EMC filter. It then uses a DC/DC converter to distribute regulated voltages (+15V, -15V, and +5V) to the rest of the system components.
    
- **Analog Input Processing (Green):** This module interfaces with various external sensors (like TATP and Transducers P1–P4). It uses signal conditioning, level converters, and constant current sources to prepare raw physical data for conversion, routing signals through a series of multiplexers (MUX).
    
- **Analog-to-Digital Conversion:** The conditioned analog signals are fed into an **A/D Converter**, which acts as the bridge between the analog and digital domains. This stage is supported by a Reference Generator to ensure precise voltage scaling during the conversion process.
    
- **Digital Processing Module (Orange):** Centered around an Intel 80960MC processor and a Transputer (XQV 300), this module handles high-level computations. It manages data storage (EEPROM, SRAM, NVRAM) and executes bus controlling, event scheduling, and timing functions before outputting the final air data.

---

## Flight Warning Systems

- **Altitude Alerting System:** This system notifies the flight crew when the aircraft deviates from a pre-selected altitude or is approaching a target altitude to ensure vertical separation and safety.

![[Pasted image 20260222222843.png]]
    
- **Overspeed Warning:** This alert triggers when the aircraft's airspeed exceeds its maximum safe operating speed, protecting the structural integrity of the airframe from aerodynamic stress.
    
- **Stall Warning:** This critical warning informs the crew when the angle of attack becomes too high and the wings can no longer produce sufficient lift, potentially leading to a loss of control.

![[Pasted image 20260222222814.png]]

---

## Flight Controls

![[Pasted image 20260222223105.png]]

---

## Flight Stabilizers and Control Surfaces

- **Horizontal Stabilizer:** This is the fixed horizontal surface of the tail assembly. It provides **longitudinal stability**, preventing the aircraft from pitching up or down uncontrollably. It acts like a small wing that creates a downward force to balance the center of gravity.
    
- **Vertical Stabilizer:** This is the fixed vertical fin on the tail. It provides **directional stability**, ensuring the aircraft flies straight and doesn't "fishtail" or wander left and right. It resists the aircraft's tendency to yaw unintentionally.
    
- **Elevators:** Attached to the rear of the horizontal stabilizer, these are primary controls used to change the aircraft's **pitch**. Moving them up forces the tail down and the nose up.
    
- **Rudder:** Attached to the trailing edge of the vertical stabilizer, this primary control surface manages **yaw**. By moving the rudder left or right, the pilot deflects airflow to push the tail in the opposite direction, turning the nose.
    
- **Stabilator:** As indicated by the bracket in your image, some aircraft combine the horizontal stabilizer and elevator into one single moving unit. Because the entire surface pivots, it is highly effective at controlling pitch, especially at high speeds.
    
- **Trim Tabs:** These are small, adjustable surfaces on the trailing edges of the elevators and rudder. They allow the pilot to neutralize control pressure, so the aircraft maintains a set altitude or heading without constant manual input.
    
- **Ailerons:** Located on the outer trailing edges of the wings, these move in opposite directions to **roll** the aircraft.
    
- **Flaps and Slats:** These "high-lift" devices on the wings increase the wing's surface area and curvature. They allow the aircraft to generate more lift at lower speeds, which is essential for safe takeoffs and landings.
    
- **Spoilers and Airbrakes:** These surfaces are used to "spoil" lift or create drag. Spoilers on top of the wing help the aircraft descend without gaining too much speed, while airbrakes are used primarily to slow the aircraft down in flight.

---

## Flaps, Slats, and Vortex Generators

Flaps and slats are "high-lift" devices used primarily during takeoff and landing to increase the wing's lift-producing capability at lower speeds. Vortex generators are small aerodynamic surfaces that improve airflow over the wing.

### Types of Flaps

![[Pasted image 20260222223933.png]]

![[Pasted image 20260222223941.png]]

Flaps are located on the trailing edge of the wing. They increase both lift and drag by changing the wing's camber (curvature) and sometimes its surface area.

- **Plain Flap:** The simplest type; the rear portion of the wing hinges downward. It increases lift but also significantly increases drag.
    
- **Split Flap:** Only the lower surface of the trailing edge hinges downward. It produces slightly more lift than a plain flap but creates much more drag, acting like an airbrake.
    
- **Slotted Flap:** Similar to a plain flap but leaves a gap (slot) between the wing and the flap. This allows high-pressure air from under the wing to flow over the top of the flap, energizing the boundary layer and delaying airflow separation.
    
- **Fowler Flap:** This type slides backward on tracks before hinging downward. It increases both the wing's camber and its total surface area, providing the greatest increase in the coefficient of lift ($C_L$).
    

### Types of Slats

![[Pasted image 20260222224012.png]]

Slats are located on the leading edge of the wing. They help maintain airflow over the top of the wing at high angles of attack, preventing a stall.

- **Fixed Slats:** These are permanently built into the leading edge with a fixed gap. They provide constant low-speed benefits but create drag at high speeds.
    
- **Automatic Slats:** These are held retracted by air pressure during high-speed flight. At low speeds and high angles of attack, aerodynamic forces pull them forward automatically to open the slot.
    
- **Powered Slats:** Controlled by the pilot via hydraulic or electric actuators, allowing them to be extended or retracted as needed for different phases of flight.
    

### Vortex Generators

![[Pasted image 20260222223905.png]]

Vortex generators are small, thin vanes usually placed in a row on the top surface of a wing or stabilizer.

- **Function:** They create tiny, high-energy vortices (whirlpools of air).
    
- **Boundary Layer:** These vortices pull faster-moving air from outside the boundary layer down toward the wing surface.
    
- **Stall Prevention:** By "energizing" the boundary layer, they prevent the airflow from separating (peeling away) from the wing at high angles of attack or high speeds, which maintains control effectiveness and delays stalls.

---

