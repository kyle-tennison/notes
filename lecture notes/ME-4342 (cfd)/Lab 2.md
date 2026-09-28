# Lab 2

![[image-141.png]]

The linear momentum equation (x axis) is:

$$\rho \int u ( \bar v \cdot \bar n) ds = R_x$$

where $R_x$ is the force on the C.V. from the plate.

Then, from what I don't understand;

$$\begin{aligned}R_x &= \rho \left[
-H U^2 + \int\limits_0^H u(L,y)^2\,dy + \int \limits_0^LU u(x, H)\, dx
\right]\\
&= \rho \left[ \int \limits _0^H u(L,y)^2\,dy - U \int\limits_0^Hu(L,y)\,dy \right]
\end{aligned}
$$


im lost

--- 

## Differential Analysis

Under the assumptions that $\delta / L \ll 1$   , the [Navier Stokes Equations](Navier%20Stokes%20Equations.md) can be reduced to an ODE:


Blasius Equation

$$2 \frac{d^3 f}{d\eta^3} + f \frac{d^2f}{d \eta^2} = 0$$

where 

$$\eta = y \sqrt{\frac{U}{\nu x}}, \qquad \frac{df}{d\eta} = \frac{u}{U}$$

with the boundary conditions:
$$f = f' = 0 \text{ at } \eta =0$$
$$\lim _{\eta \to \infty} f' = 1$$

![](excalidraw-2026-09-09-16.17.25.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-09-09-16.17.25.excalidraw.md)%%

Mathematically, this point is:

$$f'(5) = 0.99$$

Which shows the definition of the boundary layer $\delta$ being where flow is 99% of $U$. 

$$\delta \sqrt{\frac{U}{\nu x}} = 5$$

$$\frac{\delta}{x} = 5\sqrt{\frac{\nu}{Ux}}= 5 \sqrt{\frac 1{\rm Re_x}}$$
