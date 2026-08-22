# Slide 1: Title Slide

**Title:** Comprehensive Guide: Design & CFD Analysis of a Centrifugal Compressor
**Subtitle:** Step-by-Step Workflow for Real Gas (R134a) using CFturbo and ANSYS CFX

**Text Content:**

* A complete procedural guide from 1D parameter selection to 3D CFD post-processing.
* Designed to bypass common meshing, assembly, and solver divergence pitfalls.
  **Image to Insert:** `full_model_p.png` (Use as a high-quality background or hero image).

# Slide 2: Step 1 - Define Operating Parameters

**Title:** Step 1: Establishing Baseline Operating Conditions
**Text Content:**

* **Identify Target Performance:** Determine required Mass Flow Rate (1.2338 kg/s) and target Pressure Ratio (PR ~ 2.95).
* **Define Fluid Properties:** Select Real Gas R134a (Peng-Robinson Equation of State) to accurately model gas compressibility and thermodynamic behavior at high speed (36,000 RPM).
* **Determine Inlet State:** Specify Total Pressure (Pt = 336.46 kPa) and Total Temperature (Tt = 288.1 K) based on thermodynamic cycle data.
  **Image to Insert:** `Boundary condition.png`

# Slide 3: Step 2A - Impeller Aerodynamic & Blade Angle Design (CFturbo)

**Title:** Step 2A: Impeller Blade Angle (Beta) & Profile Design
**Text Content:**

* **Inlet Blade Angle (Beta 1):** Set leading-edge blade angle (Beta 1b) to match incoming relative flow angle (Beta 1) at zero incidence angle to prevent flow separation at blade leading edge.
* **Outlet Blade Angle (Beta 2):** Configure backswept blade exit angle (Beta 2b approx. 30 to 40 degrees) to control work input, stable operating range, and backward slip factor (Wiesner/Stanitz slip correction).
* **Beta-Distribution (s/s_max):** Define smooth, monotonic blade angle progression from hub to shroud using Bezier polynomial curves to minimize internal passage pressure gradients and secondary flow losses.
* **Blade Thickness & Rounding:** Apply elliptical leading-edge rounding and trailing-edge trimming to avoid localized shock formation and boundary layer separation.
  **Image to Insert:** `cfturbo old.png` (or screenshot of Blade Angle Beta-Distribution graph in CFturbo).

# Slide 4: Step 2B - Volute Casing & Cutwater Design (CFturbo)

**Title:** Step 2B: Volute Casing Geometry & Static Pressure Recovery
**Text Content:**

* **Cross-Sectional Area Progression (A_theta):** Design spiral casing cross-sections according to the constant swirl rule (r * Cu = constant) or Pfleiderer method across 0 to 360 degree azimuth angle.
* **Kinetic to Static Conversion:** The enlarging volute cross-section decelerates high-velocity gas leaving the diffuser, efficiently converting kinetic energy into static pressure recovery.
* **Cutwater (Tongue) Clearance & Angle:** Optimize cutwater tongue gap and angle (Theta 0) to minimize acoustic noise, circumferential pressure distortion, and radial forces on shaft.
* **Outlet Diffuser Extension:** Add a conical exit diffuser from volute discharge flange to ensure uniform flow delivery into downstream piping.
  **Images to Insert:** `cfturbo new.png` (shows domain division) and `cad101.png` (cut-section view of volute casing).

# Slide 5: Step 3 - Geometry Export & CAD Strategy

**Title:** Step 3: CAD Export Strategy (Crucial Step)
**Text Content:**

* **CRITICAL RULE:** Do not export single periodic blades to assemble manually in SolidWorks. This causes mesh connectivity errors and misses volute pressure recovery.
* **Correct Procedure:** Export the Full 360-Degree Fluid Domain as a "Model-Based State" directly from CFturbo.
* **CAD Cleanup (SolidWorks):** Import full STEP/IGES file to verify solid bodies. Ensure impeller, volute, and inlet pipe are distinct solid bodies without overlapping surfaces.
  **Images to Insert:** `cad2.png` (Clean 3D assembly) and `cad101.png` (Cut-section view)

# Slide 6: Step 4 - Meshing Guidelines

**Title:** Step 4: Meshing the Full Fluid Domain
**Text Content:**

* **Mesh Type:** Use high-quality unstructured tetrahedral or polyhedral mesh with boundary layer inflation (prisms).
* **Inflation Layers:** Critical for capturing wall shear and boundary layer separation (k-omega SST model).
* **Named Selections:** Properly label all boundaries before exporting: Inlet, Outlet, Impeller_Blades, Impeller_Hub, Volute_Casing.
* **Cell Count Optimization:** Ensure cell count fits within hardware memory limits while maintaining grid independence.
  **Image to Insert:** `mesh full.png`

# Slide 7: Step 5 - CFX Pre-Processing (Material Setup)

**Title:** Step 5: ANSYS CFX - Defining Real Gas
**Text Content:**

* **Why CFX?** CFX is a coupled solver highly optimized for rotating machinery and real gas thermodynamics (Fluent lacks default R134a real gas database).
* **Material Setup:**
  1. Open CFX-Pre -> Materials -> Import R134a.
  2. Set Option to Real Gas (or Peng-Robinson).
  3. Ensure Molar Mass, Critical Temperature, and Critical Pressure are defined accurately.
     **Image to Insert:** `cfx refrigerant define.png`

# Slide 8: Step 6 - CFX Pre-Processing (Domains & Physics)

**Title:** Step 6: Setting Up Domains & Frame of Reference
**Text Content:**

* **Stationary Domain:** Assign Inlet Pipe and Volute bodies to stationary fluid domain.
* **Rotating Domain (MRF):** Assign Impeller body to Rotating Domain. Set Rotational Speed (36,000 RPM) around rotation axis (Z).
* **Domain Interfaces:** Create "Frozen Rotor" or "Stage" interfaces between stationary and rotating zones to pass flow data.
* **Turbulence Model:** Select k-omega SST for accurate boundary layer prediction under adverse pressure gradients.

# Slide 9: Step 7 - CFX Pre-Processing (Boundary Conditions)

**Title:** Step 7: Boundary Conditions (Avoiding Crashes)
**Text Content:**

* **The Pitfall:** Setting mismatched Inlet/Outlet pressures causes instantaneous supersonic choking (Mach > 1) or massive backflow.
* **Recommended Setup:**
  * **Inlet:** Total Pressure (336.46 kPa) and Total Temperature (288.1 K).
  * **Outlet:** Mass Flow Rate (1.2338 kg/s).
* *Alternative:* If using Pressure Outlet, ramp pressure up slowly over iterations to prevent solver from building a "Virtual Wall" to stop backflow.

# Slide 10: Step 8 - Solver Execution & Troubleshooting

**Title:** Step 8: Solving & Identifying Errors
**Text Content:**

* **Monitor Residuals:** Track Momentum and Mass equations; they should steadily drop below 1e-4.
* **How to Read Errors:**
  * *Error: "A wall has been placed at portion(s) of an OUTLET"* -> Outlet backflow; fluid flowing backward into compressor.
  * *Error: "Fatal overflow in linear solver"* -> Solver diverged due to shockwaves or 100% backflow restriction. Fix boundary conditions to resolve.
    **Images to Insert:** `monitor.jpeg` (convergence tracking) and `err.png` / `error1.png` (divergence warnings)

# Slide 11: Step 9 - Post-Processing & Validation

**Title:** Step 9: Post-Processing Results
**Text Content:**

* **Calculate Pressure Ratio (PR):** Mass-averaged total pressure at outlet divided by inlet (PR ~ 2.9 achieved).
* **Analyze Contours:** Evaluate Static/Total Pressure and Temperature contours to ensure smooth gradients through volute.
* **Flow Visualization:** Use streamlines from inlet to verify there are no massive flow separation or recirculation zones inside blade passages.
  **Images to Insert:** `full_model_p.png` (Pressure Contour) and `full_model_T.png` (Temperature Contour)

# Slide 12: Summary Checklist & Conclusion

**Title:** Key Rules for Centrifugal Compressor CFD
**Text Content:**

1. **Always simulate full 360-degree domain:** Periodic impeller-only runs severely underpredict pressure ratio (~0.5% rise vs 2.9 target) because they miss volute diffuser recovery.
2. **Detailed CFturbo Parametric Design:** Ensure zero-incidence Beta 1 leading edge angles and backswept Beta 2 trailing edge angles are set before export.
3. **CAD Cleanliness:** Export full assemblies from CFturbo to prevent interface meshing errors.
4. **Mind the Boundaries:** Never initialize with overly aggressive pressure differentials to avoid supersonic choking and fatal solver overflows.