# Isentropic Compressible Flow Relations (Rocket Nozzle)

## Nomenclature & Terminology

### Flow Variables
- **$M$** : Mach number (dimensionless flow speed)
- **$a$** : Local speed of sound ($\text{m/s}$)
- **$v$** : Local fluid velocity ($\text{m/s}$)
- **$p$** : Local static pressure ($\text{Pa}$ or $\text{bar}$)
- **$T$** : Local static temperature ($\text{K}$)
- **$\rho$** : Local fluid density ($\text{kg/m}^3$)
- **$A$** : Cross-sectional area of the nozzle ($\text{m}^2$)
- **$q$** : Dynamic pressure ($\text{Pa}$)

### Gas Constants & Modifiers
- **$\gamma$** : Specific heat ratio (heat capacity ratio $C_p/C_v$)
- **$R$** : Specific gas constant ($\text{J/kg}\cdot\text{K}$)
- **$t$** *(subscript)* : Total or Stagnation conditions (where flow velocity $v = 0$)
- **$*$** *(superscript/subscript)* : Critical or Sonic conditions (where Mach number $M = 1$, occurs at the nozzle throat)

---

## Nozzle Regimes
- **Subsonic ($M < 1$)** : Converging section before the throat.
- **Sonic ($M = 1$)** : Nozzle throat ($A^*$).
- **Supersonic ($M > 1$)** : Diverging section after the throat.

---

## Governing Isentropic Equations

### 1. Mach Number Definition
$$M = \frac{v}{a}$$

### 2. Speed of Sound
$$a = \sqrt{\gamma \frac{p}{\rho}} = \sqrt{\gamma R T}$$

### 3. Isentropic Relation (Constant Entropy State)
$$\frac{p}{\rho^\gamma} = \text{Constant} = \frac{p_t}{\rho_t^\gamma}$$

### 4. Pressure Ratio in Terms of Density and Temperature
$$\frac{p}{p_t} = \left(\frac{\rho}{\rho_t}\right)^\gamma = \left(\frac{T}{T_t}\right)^{\frac{\gamma}{\gamma - 1}}$$

### 5. Dynamic Pressure
$$q = \frac{1}{2}\rho v^2 = \frac{\gamma}{2} p M^2$$

### 6. Static to Total Pressure Ratio
$$\frac{p}{p_t} = \left(1 + \frac{\gamma - 1}{2} M^2\right)^{-\frac{\gamma}{\gamma - 1}}$$

### 7. Static to Total Temperature Ratio
$$\frac{T}{T_t} = \left(1 + \frac{\gamma - 1}{2} M^2\right)^{-1}$$

### 8. Static to Total Density Ratio
$$\frac{\rho}{\rho_t} = \left(1 + \frac{\gamma - 1}{2} M^2\right)^{-\frac{1}{\gamma - 1}}$$

### 9. Area-Mach Number Relation (Area Ratio)
$$\frac{A}{A^*} = \frac{\left(\frac{\gamma + 1}{2}\right)^{-\frac{\gamma + 1}{2(\gamma - 1)}} \left(1 + \frac{\gamma - 1}{2} M^2\right)^{\frac{\gamma + 1}{2(\gamma - 1)}}}{M}$$
