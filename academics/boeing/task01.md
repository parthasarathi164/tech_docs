# making a 2D simulator of the strut

### parameters table

| **Parameter**                     | **Symbol** | **Typical Range**                | **Units** | **Impact on Performance**                                                                   |
| --------------------------------- | ---------- | -------------------------------- | --------- | ------------------------------------------------------------------------------------------- |
| **Aircraft Mass** (per strut)     | $m$        | $500 - 5,000$                    | kg        | Higher mass increases total energy and stroke required.                                     |
| **Sink Rate** (Vertical Velocity) | $V_s$      | $2.0 - 4.5$                      | m/s       | **Critical.** Energy scales with $V_s^2$. Certification usually requires $\approx 3.0$ m/s. |
| **Piston Diameter**               | $D_p$      | $40 - 150$                       | mm        | Larger area ($A_p$) increases both air and oil forces.                                      |
| **Max Stroke**                    | $S_{max}$  | $150 - 500$                      | mm        | Physical limit. You want your design stroke to be $\approx 85\%$ of this.                   |
| **Initial Gas Pressure**          | $P_0$      | $10 - 50$                        | bar       | Controls the "static" height (taxiing). Higher $P_0$ makes the strut stiffer.               |
| **Initial Gas Volume**            | $V_0$      | $1.2 \times (A_p \cdot S_{max})$ | $m^3$     | Total volume of Nitrogen. Affects the progressiveness of the "spring."                      |
| **Orifice Diameter**              | $d_o$      | $5 - 25$                         | mm        | **The Tuning Knob.** Smaller holes increase damping (heat dissipation).                     |
| **Oil Density**                   | $\rho$     | $850 - 900$                      | $kg/m^3$  | Usually fixed by the fluid type (e.g., MIL-H-5606).                                         |
| **Polytropic Exponent**           | $n$        | $1.1 - 1.4$                      | -         | $1.1$ for slow taxi (isothermal), $1.3$ for fast impact (adiabatic).                        |
