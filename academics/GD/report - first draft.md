Here are all the mathematical formulae used in the code:

---

## 1. Theta–Beta–M Relation (Oblique Shock)

The core governing equation relating wedge angle θ, shock wave angle β, and freestream Mach number M:

$$\tan\theta = \frac{2}{\tan\beta} \cdot \frac{M^2 \sin^2\beta - 1}{M^2(\gamma + \cos 2\beta) + 2}$$

where γ = 1.4 (ratio of specific heats for air).

---

## 2. Mach Angle (Sonic Limit / Initial Guess)

The Mach angle μ is the minimum possible shock angle, used as the starting guess when solving for β:

$$\mu = \arcsin\left(\frac{1}{M}\right)$$

---

## 3. Shock Intersection Point

The bottom incident shock travels as a straight line from the origin with slope tan(β_bot), and the top shock from (0, h) with slope −tan(β_top). Setting them equal:

$$y = \tan(\beta_{\text{bot}}) \cdot x \quad \text{(bottom shock line)}$$

$$y = h - \tan(\beta_{\text{top}}) \cdot x \quad \text{(top shock line)}$$

Solving simultaneously for the intersection:

$$x_{\text{int}} = \frac{h}{\tan\beta_{\text{bot}} + \tan\beta_{\text{top}}}$$

$$y_{\text{int}} = \tan(\beta_{\text{bot}}) \cdot x_{\text{int}}$$

---

## 4. Slip Line Angle (Asymmetric Case)

When the two wedge angles differ (θ_bot ≠ θ_top), the two streams crossing the shocks have different flow directions. The slip line is approximated as bisecting the deflection difference:

$$\alpha_{\text{slip}} = \frac{\theta_{\text{bot}} - \theta_{\text{top}}}{2}$$

The slip line then extends from the intersection point as:

$$y = y_{\text{int}} + \tan(\alpha_{\text{slip}}) \cdot (x - x_{\text{int}})$$

---

## 5. Wedge / Ramp Geometry

The vertical rise of each ramp over the fixed ramp length L_ramp = 1.5 m:

$$\Delta y_{\text{bot}} = \tan(\theta_{\text{bot}}) \cdot L_{\text{ramp}}$$

$$\Delta y_{\text{top}} = \tan(\theta_{\text{top}}) \cdot L_{\text{ramp}}$$

giving duct inner wall positions:

$$y_{\text{wall,bot}} = \tan(\theta_{\text{bot}}) \cdot L_{\text{ramp}}, \qquad y_{\text{wall,top}} = h - \tan(\theta_{\text{top}}) \cdot L_{\text{ramp}}$$

---

## Summary Table

|Formula|Symbol|Purpose|
|---|---|---|
|θ–β–M relation|θ, β, M|Oblique shock angle|
|μ = arcsin(1/M)|μ|Mach / sonic cone angle|
|x_int = h / (tan β_bot + tan β_top)|x_int|Shock intersection x|
|y_int = tan(β_bot) · x_int|y_int|Shock intersection y|
|α_slip = (θ_bot − θ_top) / 2|α_slip|Slip line direction|
|Δy = tan(θ) · L_ramp|Δy|Ramp height|
