# Navier Stokes Equations

The Navier-Stokes equations are partial differential equations that describe fluid motion.

Mathematically, they express the conservation of momentum for Newtonian fluids, along with the conservation of mass. They do this by applying [Newton's Second Law](Galileo's%20Relativity%20Principle.md#^newtons-second-law) to fluid motion, while also assuming that the stress in the fluid as a sum of pressure and a "diffusing viscous term."

The solution to these equations is a flow velocity field. After finding velocity, you can then solve for pressure or temperature. 

## Derivation

### Newtonian Fluids

A Newtonian fluid satisfies the following assumptions:

1. The stress tensor is a linear function of the strain rate tensor (or, equivalently, the velocity gradient)
2. The fluid is isotropic
3. At rest, $\nabla \cdot \boldsymbol \tau = 0$ 

Mathematically, this means that:

$$\tau _{ij}=\mu\left( \frac{\partial u_i}{\partial x_j}+\frac{\partial u_j}{\partial x_i} \right)+\delta_{ij}\lambda \sum_{k}\frac{\partial u_k}{\partial x_k}$$

alternatively expressed as:

$$\boldsymbol \tau = \mu \left( \nabla \textbf u + (\nabla \textbf u)^T \right)+\lambda (\nabla \cdot \textbf u) \textbf I$$

where $\mu$ and $\lambda$ are proportionality constants:
- $\mu$ is the shear viscosity, usually called **viscosity**
- $\lambda$ is the volume viscosity, usually called **bulk viscosity**
	- This influences changes in volume and is often negligible

> $k$ is a set of the axes (e.g., for cartesian $k=\{x, y, z\}$, which is more commonly expressed as $k=\{1, 2, 3\}$ as part as the Einstein summation convention)


Substituting this into the the [Cauchy Momentum Equation](Cauchy%20Momentum%20Equation.md#^momentum-equation) yield the **Navier-Stokes Equations**:

$$\rho\left(\frac{\partial \textbf u }{\partial t}+\textbf u \cdot \nabla \textbf u \right)=-\nabla p + \nabla \cdot \Big[\mu \left(\nabla \textbf u +(\nabla \textbf u)^T\right)\Big]+ \nabla \cdot \Big[ \lambda (\nabla \cdot \textbf u) \textbf I \Big] + \textbf f $$


This is typically accompanied by the [Continuity Equation](Cauchy%20Momentum%20Equation.md#^continuity-equation):

$$0=\frac{\partial \rho}{\partial t} + \nabla \cdot ( \rho \textbf{u})$$

In addition to this, an accompanying equation of state for the conservation of energy is needed. This is of the form:

$$\rho \frac{Dh}{Dt}=\frac{Dp}{Dt}+\nabla \cdot(k\nabla T)+\Phi$$

where $h$ is specific enthalpy, $T$ is temperature, and $\Phi$ is a function that represents the dissipation of energy due to viscous friction:

$$\Phi = \mu \left( 2 \left(\frac{\partial u}{\partial x}\right)^2+2 \left(\frac{\partial v}{\partial y}\right)^2+2 \left(\frac{\partial w}{\partial z}\right)^2 + 2 \left(\frac{\partial v}{\partial x} +\frac{\partial u}{\partial y}\right)^2 + \left(\frac{\partial w}{\partial y} +\frac{\partial v}{\partial z}\right)^2 +\left(\frac{\partial u}{\partial z} +\frac{\partial w}{\partial x}\right)^2\right)+\lambda (\nabla \cdot \textbf u )^2$$

> The equation of state won't apply for incompressible fluids; for these, you satisfy the missing constraint using $\nabla \cdot \textbf u = 0$

### Incompressible Fluids

For an **incompressible fluid**:
1. $\lambda = 0$
2. $\mu = \text{const.}$ 
3. $\nabla \cdot \textbf u = 0$ 


Because $\lambda$ is assumed to be zero, the equation reduces to:

$$\rho\left(\frac{\partial \textbf u }{\partial t}+\textbf u \cdot \nabla \textbf u \right)=-\nabla p + \nabla \cdot \Big[\mu \left(\nabla \textbf u +(\nabla \textbf u)^T\right)\Big] + \textbf f $$

And, because $\mu$ is constant, we can re-arrange the RHS as:

$$\rho\left(\frac{\partial \textbf u }{\partial t}+\textbf u \cdot \nabla \textbf u \right)=-\nabla p + \mu \nabla \cdot \Big[ \left(\nabla \textbf u +(\nabla \textbf u)^T\right)\Big] + \textbf f $$

And, because $\nabla \cdot \textbf u=0$, the term $\nabla \cdot (\nabla \textbf u + (\nabla \textbf u)^T)$ reduces to $\nabla^2 \textbf u$ , leaving:


$$\rho\left(\frac{\partial \textbf u }{\partial t}+\textbf u \cdot \nabla \textbf u \right)=-\nabla p + \mu \nabla^2 \textbf u + \textbf f $$

Or, once rearranged to isolate $\partial \textbf u / \partial t$: 

$$\rho \frac{\partial \textbf u}{\partial t}= -\nabla p+\mu \nabla ^2 \textbf u + \textbf f-\rho(\textbf u \cdot \nabla \textbf u)$$

### Non-dimensionalized Pressure

If you define a $\textbf f^\star$ that includes the pressure gradient, that is:

$$\textbf f^\star=\frac{1}{\rho}\nabla p+\textbf f$$

You can simplify the equation at the cost of simulation accuracy.

### Incompressible Pressure Poisson 

If you take the divergence of both sides of:

$$\rho\left(\frac{\partial \textbf u }{\partial t}+\textbf u \cdot \nabla \textbf u \right)=-\nabla p + \mu \nabla^2 \textbf u + \textbf f $$

You get:

$$
\begin{aligned}

\nabla \cdot \Bigg [\rho\left(\frac{\partial \textbf u }{\partial t}+\textbf u \cdot \nabla \textbf u \right) \Bigg ]&=\nabla \cdot (-\nabla p + \mu \nabla^2 \textbf u + \textbf f) \\

\underbrace{\rho}_{\text{const.}}\Bigg [\nabla \cdot\frac{\partial \textbf u }{\partial t}+\nabla\cdot\left(\textbf u \cdot \nabla \textbf u \right) \Bigg ]&=\nabla \cdot (-\nabla p + \mu \nabla^2 \textbf u + \textbf f) \\

{\rho}\Bigg [ \frac{\partial }{\partial t}\cancel{(\nabla \cdot u)}  +\nabla\cdot\left(\textbf u \cdot \nabla \textbf u \right) \Bigg ]&=\nabla \cdot (-\nabla p + \mu \nabla^2 \textbf u + \textbf f) \\

{\rho}\nabla\cdot\left(\textbf u \cdot \nabla \textbf u \right) &=\nabla \cdot (-\nabla p + \mu \nabla^2 \textbf u + \textbf f) \\

{\rho}\nabla\cdot\left(\textbf u \cdot \nabla \textbf u \right) &=-\nabla^2p+\mu\nabla \cdot \nabla^2\textbf u+\nabla\cdot \textbf f \\

{\rho}\nabla\cdot\left(\textbf u \cdot \nabla \textbf u \right) &=-\nabla^2p+\mu\nabla^2 (\cancel{\nabla\cdot\textbf u})+\nabla\cdot \textbf f \\

{\rho}\nabla\cdot\left(\textbf u \cdot \nabla \textbf u \right) &=-\nabla^2p+\nabla\cdot \textbf f \\

\nabla^2 p &= -\rho \nabla \cdot(\textbf u \cdot \nabla \textbf u) + \nabla \textbf f

\end{aligned}
$$

This is known as the **Pressure Poisson equation**. 




## References

- https://en.wikipedia.org/wiki/Derivation_of_the_Navier%E2%80%93Stokes_equations