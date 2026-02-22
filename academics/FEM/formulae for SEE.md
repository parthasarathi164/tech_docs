## MOI for common sections

Rectangle:
$I = \frac{b h^3}{12}$

Hollow Rectangle:
$I = \frac{B H^3 - b h^3}{12}$

Circle (diameter = D):
$I = \frac{\pi D^4}{64}$

Hollow Circle (outer diameter = D, inner diameter = d):
$I = \frac{\pi (D^4 - d^4)}{64}$

I-Section:
$I = \frac{b_f h^3}{12} - \frac{(b_f - t_w)(h - 2 t_f)^3}{12}$

## deflection formulae

Cantilever Beam – Point Load at Free End (P):
$\delta_{max} = \frac{P L^3}{3 E I}$

Cantilever Beam – UDL over Full Length (w):
$\delta_{max} = \frac{w L^4}{8 E I}$

Cantilever Beam – UVL (0 at fixed end → w at free end):
$\delta_{max} = \frac{w L^4}{30 E I}$

Cantilever Beam – UVL (w at fixed end → 0 at free end):
$\delta_{max} = \frac{w L^4}{20 E I}$

## important matrices formulae

1D Bar Element (Axial):
$$
k = \frac{EA}{L}
\begin{bmatrix}
1 & -1 \\
-1 & 1
\end{bmatrix}
$$

1D Beam Element:
$$\begin{bmatrix} F_{y1} \\ M_1 \\ F_{y2} \\ M_2 \end{bmatrix} = \frac{EI}{L^3} \begin{bmatrix} 12 & 6L & -12 & 6L \\ 6L & 4L^2 & -6L & 2L^2 \\ -12 & -6L & 12 & -6L \\ 6L & 2L^2 & -6L & 4L^2 \end{bmatrix} \begin{bmatrix} v_1 \\ \theta_1 \\ v_2 \\ \theta_2 \end{bmatrix}$$

1D Bar Element (Axial Strain):
$$
\varepsilon 
= 
\begin{bmatrix}
-\frac{1}{L} & \frac{1}{L}
\end{bmatrix}
\begin{bmatrix}
u_1 \\
u_2
\end{bmatrix}
= 
-\frac{u_1}{L} + \frac{u_2}{L}
$$

1D Beam Element (Bending Strain → Curvature):
$$
\kappa 
=
\begin{bmatrix}
\frac{12}{L^3} & \frac{6}{L^2} & -\frac{12}{L^3} & \frac{6}{L^2}
\end{bmatrix}
\begin{bmatrix}
w_1 \\
\theta_1 \\
w_2 \\
\theta_2
\end{bmatrix}
=
\frac{12 w_1}{L^3}
+ \frac{6 \theta_1}{L^2}
- \frac{12 w_2}{L^3}
+ \frac{6 \theta_2}{L^2}
$$

Equivalent Nodal Force Vector for a Uniformly Distributed Load (UDL):
$$
\mathbf{f}^e =
\begin{bmatrix}
F_1 \\
M_1 \\
F_2 \\
M_2
\end{bmatrix}
=
\begin{bmatrix}
\displaystyle \frac{wL_e}{2} \\
\displaystyle \frac{wL_e^2}{12} \\
\displaystyle \frac{wL_e}{2} \\
\displaystyle -\frac{wL_e^2}{12}
\end{bmatrix}
$$

Equivalent Nodal Force Vector for a Uniformly Varying Load (UVL):
$$
\mathbf{f}^e =
\begin{bmatrix}
F_1 \\
M_1 \\
F_2 \\
M_2
\end{bmatrix}
=
\begin{bmatrix}
\dfrac{L_e}{20}\left(7w_1 + 3w_2\right) \\
\dfrac{L_e^2}{60}\left(3w_1 + 2w_2\right) \\
\dfrac{L_e}{20}\left(3w_1 + 7w_2\right) \\
-\dfrac{L_e^2}{60}\left(2w_1 + 3w_2\right)
\end{bmatrix}
$$

>NOTE: where $w_1$ and $w_2$ are min and max loads

---

## **Lagrange Polynomial Formula (1D)**

For a set of $n$ points, the $i$-th Lagrange polynomial is:

$$L_i(\xi) = \prod_{j=1, j \neq i}^{n} \frac{\xi - \xi_j}{\xi_i - \xi_j}$$

---

## Truss formulae

### **Elemental Stiffness Matrix ($[K]$)**

The global stiffness matrix relates global nodal forces to global nodal displacements:

$$[K] = \frac{AE}{L} \begin{bmatrix} l^2 & lm & -l^2 & -lm \\ lm & m^2 & -lm & -m^2 \\ -l^2 & -lm & l^2 & lm \\ -lm & -m^2 & lm & m^2 \end{bmatrix}$$

### **Axial Strain Formula ($\epsilon$)**

The strain depends on the global nodal displacements $\{q\} = [u_1, v_1, u_2, v_2]^T$ and the direction cosines:

$$\epsilon = \frac{1}{L} \begin{bmatrix} -l & -m & l & m \end{bmatrix} \begin{Bmatrix} u_1 \\ v_1 \\ u_2 \\ v_2 \end{Bmatrix}$$

---

## Load vectors for body and traction force

For a 1D bar element with a constant body force $f_x$ (force per unit volume), cross-sectional area $A$, and length $L$, the body force vector $\{f_b\}$ is:

$$\{f_b\} = \frac{f_x AL}{2} \begin{Bmatrix} 1 \\ 1 \end{Bmatrix}$$

For a 1D bar element with a constant traction force $T_x$ (force per unit length) applied over the entire length $L$, the traction force vector $\{f_t\}$ is:

$$\{f_t\} = \frac{T_x L}{2} \begin{Bmatrix} 1 \\ 1 \end{Bmatrix}$$

---

