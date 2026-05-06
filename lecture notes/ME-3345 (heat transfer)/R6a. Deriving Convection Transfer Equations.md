# R6a. Deriving Convection Transfer Equations


The [Heat Diffusion Equation](R2.%20Conduction.md#Heat%20Diffusion%20Equation) was a set of partial differential equations that could be used to solve for the heat transfer through a solid. Now, we wish to do the same for convection. These equations consider fluid mechanics along with heat transfer, and are accordingly very complicated.

Appendix E of the book provides this derivation. However, I incorporate bits from Chapter 6 for clarity.

## Species Concentration

In [R6. Convection](R6.%20Convection.md) we talked about how convection can transfer heat, but it can also transfer mass.

Imagine that the surface of some object bleeds some gas into an adjacent fluids stream. For example, this might be sweat being evaporated into the wind. The main idea is that the *species molar concentration* (${\rm kmol/m^3}$) is different at the surface than in the stream. Mathematically, we say:

$$C_{A,s}\ne C_{A,\infty}$$

Which is analogous to $T_{s}\ne T_{\infty}$ or $u_0=0\ne u_\infty$ . The subscript $A$ refers to *species* A. A problem may contain other species, hence the subscript. 

Much like [Newton's Law of Cooling](lecture%20notes/ME-3345%20(heat%20transfer)/R1.%20Introduction.md#Newton's%20Law%20of%20Cooling), the *molar flux* of the species, which is specifically species A in this case, is given by:

$$N_A'' = h_m(C_{A,s}-C_{A,\infty})$$
^molar-flux

where $h_m \dot = {\rm m/s}$ is the *convection mass transfer coefficient* and $N_A \dot = \rm{kmol/s}$ is the aforementioned molar flux.  As mentioned in [R6. Convection](R6.%20Convection.md), this quantity is *local* to the point on the body (like all other fluxes) and needs to be integrated to use with the rest of the body.

For heat transfer by convection, we used an [average heat transfer convection coefficient](R6.%20Convection.md#^average-h) $\bar h$. The same can be done for mass transfer:

$$N_A=\bar h_m A_s(C_{A,s}-C_{A,\infty}), \qquad \bar h_m = \frac{1}{A_s} \iint_s h_m\,dS$$

Here, $N_A$ is the *total molar transfer rate*.

### Mass Flux

Instead of Molar Flux, you can express mass flux $n_A'' \dot = \rm kg/s \cdot m^2$ or mass transfer rate $n_a \dot = \rm kg/s$ by multiplying the equations for $N_A''$ and $N_A$ by their molecular weight $\mathscr M_A$. The molar concentrations $C$ multiplied by molar mass give density:

$$C \left[\frac{\rm \cancel{kmol}}{\rm m^3}\right] \times \mathscr M \left[\frac{\rm kg}{\rm\cancel{ kmol}}\right] = \rho \left[ \frac{\rm kg}{\rm m^3}\right] $$
This means that mass flux and mass transfer rate an be expressed as:

$$n''_A = h_m (\rho_{A,s} - \rho_{A,\infty}), \qquad n_a=\bar h_mA_s(\rho_{A,s}, \rho_{A,\infty})$$
^mass-flux-and-mass-transfer-rate
### Concentration Boundary Layer

Like heat transfer, mass transfer has its own boundary layer. There is a gradient from $C_{A,s}\to C_{A,\infty}$ , just like temperature.The thickness $\delta_c$ is defined for the region where:

$$\frac{C_{A,s}-C_A}{C_{A,s}-C_{A,\infty}} = 0.99$$

**Fick's law**, which describes diffusion, gives the molar flux at the boundary layer:

$$N_A'' = -D_{AB}\left. \frac{\partial C_A}{\partial y}\right|_{y=0}$$

where $D_{AB}$ is the *binary diffusion coefficient*. At $y=0$, because there is no fluid motion, there is no *advection* (bulk motion) and only diffusion, meaning that Fick's law is an accurate application, similar to how we applied conduction to the fluid at the boundary layer when determining the thermal boundary layer BC.

This can be used with the [molar flux](#^molar-flux) equation above to solve for the convection mass transfer coefficient $h_m$:

$$h_m = \frac{-D_{AB} \partial C_A/\partial y|_{y=0}}{C_{A,s}-C_{A,\infty}}$$

You can do the same with the [mass flux](#^mass-flux-and-mass-transfer-rate) equation above:

$$h_m = \frac{-D_{AB}\partial \rho_A/\partial y|_{y=0}}{\rho_{A,s}-\rho_{A,\infty}}$$

## Derivation

The following is limited to 2D. It is assumed that $dz=1$ (unit).
### Conservation of Mass

From the [Cauchy Momentum Equation](Cauchy%20Momentum%20Equation.md), the [continuity equation](Cauchy%20Momentum%20Equation.md#^continuity-equation) states:

$$\underbrace{0=\frac{\partial \rho}{\partial t} + \nabla \cdot ( \rho \textbf{u})}_{\text{Continuity Equation}}$$

Which is derived by simply enforcing that the divergence of mass into a fixed volume must be accounted for by a change in density. For *incompressible* fluids, the density is immutible so the equations reduce to:

$$\nabla\cdot  \mathbf u = 0$$

In 2D, this expands simply to:

$$\frac{\partial u}{\partial x} + \frac{\partial v}{\partial y} = 0$$

### Navier Stokes

The [Navier Stokes Equations](Navier%20Stokes%20Equations.md) for a Newtonian fluid are:

$$\rho \frac{\partial \textbf u}{\partial t}= -\nabla p+\mu \nabla ^2 \textbf u + \textbf f-\rho(\textbf u \cdot \nabla \textbf u)$$

At steady state $\partial \mathbf u / \partial t \to 0$, and the equations reduce to:

$$\rho(\textbf u \cdot \nabla \textbf u) = -\nabla p+\mu \nabla ^2 \textbf u + \textbf f$$

In 2D, this expands to:

$$
\rho
\begin{bmatrix}
\displaystyle u\frac{\partial u}{\partial x}+v\frac{\partial u}{\partial y}\\
\displaystyle v\frac{\partial v}{\partial x} + v \frac{\partial v}{\partial y}
\end{bmatrix} = 
-\begin{bmatrix}
\displaystyle \frac{\partial p}{\partial x}\\
\displaystyle \frac{\partial p}{\partial y}
\end{bmatrix}
+ \mu 
\begin{bmatrix}
\displaystyle\frac{\partial^2u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2}\\
\displaystyle\frac{\partial^2 v}{\partial x^2} + \frac{\partial^2 v}{\partial y^2}
\end{bmatrix}
+
\begin{bmatrix}
X \\ Y
\end{bmatrix}
$$

Or, as scalar equations

$$
\rho\left(u\frac{\partial u}{\partial x}+v\frac{\partial u}{\partial y}\right)
=
-\frac{\partial p}{\partial x}
+ \mu \left(\frac{\partial^2u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2}\right)
+ X
$$
^scalar-ns-x

$$
\rho\left(v\frac{\partial v}{\partial x}+v\frac{\partial v}{\partial y}\right)
=
-\frac{\partial p}{\partial y}
+ \mu \left(\frac{\partial^2 v}{\partial x^2} + \frac{\partial^2 v}{\partial y^2}\right)
+ Y
$$


### Conservation of Energy

We also need to perform a thermodynamic analysis to consider the transfer of energy for a control volume.

![[IMG_2080.jpeg]]

The two modes of heat transfer are conduction/diffusion and advection. We also need to consider any work done on the control volume by the fluid motion. 

---

The **energy by advection** is given by:

$$\dot E_{\rm adv} = \rho u \left(e + \frac{V^2}{2} \right)dy\,\cancelto{1}{dz} $$

This is just the mass flow rate

$$\dot m = \underbrace{u \cdot dy\,dz}_{\displaystyle \dot V\!\!\!\!\!{-}}\cdot \rho = \rho \dot V\!\!\!\!\!-$$

times energy. This is exactly what was done in thermo. You can see some of that [here](0.%20Control%20Volume%20Work.md). The $e$ represents the internal (thermal) energy. In the $x$ axis, there is advection into and out of the control volume. This means that the net energy transfer form advection is:

$$
\begin{aligned}
\dot E_{{\rm adv},x} - \dot E_{{\rm adv}, {x+dx}} &= \rho u \left(e + \frac{V^2}{2} \right)\,dy - \left \{ \underbrace{
\rho u \left(e + \frac{V^2}{2} \right)+\frac{\partial}{\partial x}\left[ \rho u \left(e + \frac{V^2}{2} \right)\right]dx}_\text{1st Order Taylor Expansion}
\right\}dy\\
&= - \frac{\partial }{\partial x}\left[ \rho u \left(e + \frac{V^2}{2}\right) \right]\,dx\,dy
\end{aligned}
$$


---

There is also e**nergy transfer by conduction** and diffusion. The diffusion of one species A into another species B is complicated and often negligible when gasses aren't reacting, so we only consider conduction here. However, *its important to check that this is indeed negligible*. The conduction can be used simply from [Fourier's Law](lecture%20notes/ME-3345%20(heat%20transfer)/R1.%20Introduction.md#Fourier's%20Law), applied to both sides. For one side, it is simply:

$$\dot E_{{\rm cond},x} = -\left(k \, \frac{\partial T}{\partial x}\right)\,dy\,\cancelto 1{dz}$$
So, when applied to both sides:

$$
\begin{aligned}
\dot E_{{\rm cond}, x} - \dot E_{{\rm cond}, x+dx} &= -\left(k \, \frac{\partial T}{\partial x}\right)\,dy - \left \{
\underbrace{
-k \frac{\partial T}{\partial x} - \frac{\partial}{\partial x}\left[
k \frac{\partial T}{\partial x}
\right] dx
}_{\text{1st Order Taylor Expansion}}
\right\}dy\\
&=\frac{\partial }{\partial x}\left(k\frac{\partial T}{\partial x}\right)\,dx\,dy
\end{aligned}
$$


---

Finally, the **energy transfer by work** of the fluid is given by:

$$\dot W_{{\rm net},x} = (Xu)\,dx\,dy + \frac{\partial }{\partial x}[(\sigma_{xx}-p)u]\,dx\,dy + \frac{\partial}{\partial y}(\tau_{xy}u)\,dx\,dy$$

The $(X u)\,dx\,dy$ term is force from the $X$ field times the velocity $u$, giving power from the acceleration field. $X$ is one component of the  [body forces](Cauchy%20Momentum%20Equation.md#^body-forces) described in the derivation of the [Cauchy Momentum Equation](Cauchy%20Momentum%20Equation.md). We see that it needs to be multiplied by the differential volume to be converted into a force, hence the $dx,dy$.

The other terms are (I think) from the [Conservation form](Cauchy%20Momentum%20Equation.md#Conservation%20form) of the Cauchy Momentum Equation. 

---

*Asserting the conservation of energy with these three equations* gives the final equation. This includes the $y$ components of the equations that aren't shown above.

$$
\begin{aligned}
& - \frac{\partial}{\partial x}\left[ \rho u \left(e + \frac{V^2}{2}\right) \right]- \frac{\partial}{\partial y}\left[ \rho u \left(e + \frac{V^2}{2}\right) \right] +  \frac{\partial}{\partial x}\left(k \frac{\partial T}{\partial x}\right) + \frac{\partial}{\partial y}\left(k \frac{\partial T}{\partial y}\right)\\
&+ (Xu + Yu) - \frac{\partial}{\partial x}(pu) - \frac{\partial}{\partial y}(pv) + \frac{\partial}{\partial x}(\sigma_{xx}u+\tau_{xy}v) + \frac{\partial}{\partial y}(\tau_{yx}u+\sigma_{yy}v)+\dot q =0 
\end{aligned}
$$

However, this is rarely used to solve equations. Instead, the **thermal energy equation** is obtained by dotting the above [2D Navier Stokes](#Navier%20Stokes) by $\mathbf u$ and subtracting the results from this evil equation above. This gives the following:

$$
\boxed{\rho u \frac{\partial e}{\partial x} + \rho v \frac{\partial e}{\partial y} = \frac{\partial}{\partial x}\left( k \frac{\partial T}{\partial x}\right) + \frac{\partial}{\partial y} \left(k \frac{\partial T}{\partial y} \right) - p \left(\frac{\partial u}{\partial x}  +\frac{\partial v}{\partial y} \right) + \mu \Phi + \dot q}
$$

The term $p \left(\frac{\partial u}{\partial x}  +\frac{\partial v}{\partial y} \right)$ represents the conversion between mechanical work and energy, and $\mu \Phi$ represents the **viscous dissipation**. It is defined as:

$$\mu \Phi \equiv \mu \left\{
\left(\frac{\partial u}{\partial y} + \frac{\partial v}{\partial x}  \right)^2 + 2 \left[ \left( \frac{\partial u}{\partial x} \right)^2 + \left( \frac{\partial v}{\partial y} \right)^2 \right]- \frac 23 \left( \nabla \cdot \mathbf u \right )^2
\right\}$$

The $\nabla \cdot \mathbf u =0$ when the fluid is incompressible, reducing it to:

$$
\mu \Phi = \mu \left\{
\left(\frac{\partial u}{\partial y} + \frac{\partial v}{\partial x}  \right)^2 + 2 \left[ \left( \frac{\partial u}{\partial x} \right)^2 + \left( \frac{\partial v}{\partial y} \right)^2 \right]
\right\}
$$

If the gas is a [perfect gas](https://en.wikipedia.org/wiki/Perfect_gas), the equation reduces to:

$$
{\rho c_p \left( u \frac{\partial T}{\partial x} + v \frac{\partial T}{\partial y} \right) = \frac{\partial}{\partial x}\left( k \frac{\partial T}{\partial x}\right) + \frac{\partial}{\partial y} \left(k \frac{\partial T}{\partial y} \right) - p \left(\frac{\partial u}{\partial x}  +\frac{\partial v}{\partial y} \right) + \mu \Phi + \dot q}
$$

If $k$ is constant, this can be written as:

$$
\begin{aligned}
\rho c_p \left( u \frac{\partial T}{\partial x} + v \frac{\partial T}{\partial y} \right) &= k \left( \frac{\partial^2T}{\partial x^2} + \frac{\partial ^2 T}{\partial y ^2}  \right) - p \left(\frac{\partial u}{\partial x}  +\frac{\partial v}{\partial y} \right) + \mu \Phi + \dot q
\\\\ \rho c_p \mathbf u \cdot \nabla T&= k \nabla^2T - p(\nabla \cdot \mathbf u)+ \mu \Phi + \dot q
\end{aligned}
$$

### Conservation of Species

I suppose you could derive this from the [Law of Definite Proportions](https://en.wikipedia.org/wiki/Law_of_definite_proportions). Basically, the composition ratio of species is conserved.

The mass of some species entering a volume is caused from both *advection and diffusion*. For advection, it is simply:

$$\dot m_{\rm A, adv, x} - \dot m_{\rm A, adv, x+dx} = (\rho_Au)\,dy - \left\{
\underbrace{\rho_Au + \frac{\partial}{\partial x}\left[\rho _A u\right] dx}_\text{1st Order Taylor Expansion}
\right\} dy = -\frac{\partial}{\partial x}(\rho_Au)\,dx\,dy$$

For diffusion, Fick's Law is used:

$$
\begin{aligned}
\dot m_{\rm A, diff, x} - \dot m_{\rm A, diff, x+dx}&=  
\left(-D_{AB}\frac{\partial \rho_A}{\partial x}\right)\,dy - \left\{
\underbrace{-D_{AB}\frac{\partial \rho_A}{\partial x} + \frac{\partial}{\partial x}\left[-D_{AB}\frac{\partial \rho_A}{\partial x}\right] dx}_\text{1st Order Taylor Expansion}
\right\} dy\\& = \frac{\partial}{\partial x}\left(D_{AB}\frac{\partial \rho_A}{\partial x}\right)\,dx\,dy
\end{aligned}
$$

You can combine this with the y axis, and express it as:

$$u \frac{\partial \rho_A}{\partial x}+v \frac{\partial \rho_A}{\partial y} = \frac{\partial }{\partial x} \left( D_{AB} \frac{\partial \rho_A}{\partial x} \right) +\frac{\partial }{\partial y}\left( D_{AB}\frac{\partial \rho_A}{\partial y} \right) + \dot n_A$$

where $\dot n_A$ is the mass flux rate. Note that this equation allows for $\dot M_{A,g}$, or some *generated* specimen that might bleed out of the system (e.g., sweat).

You can equivalently express this on a molar basis instead:

$$u \frac{\partial C_A}{\partial x} + v \frac{\partial C_A}{\partial y} =  \frac{\partial }{\partial x} \left( D_{AB} \frac{\partial C_A}{\partial x} \right) +\frac{\partial }{\partial y}\left( D_{AB}\frac{\partial C_A}{\partial y} \right) + \dot N_A$$

If $D_{AB}$ is constant, this can be written as:

$$
\begin{aligned}
u \frac{\partial C_A}{\partial x} + v \frac{\partial C_A}{\partial y} &=  D_{AB}\left( \frac{\partial^2 C_A}{\partial x^2} + \frac{\partial^2 C_A}{\partial y^2} \right)+ \dot N_A\\\\
\mathbf u \cdot \nabla C_A &= D_{AB}\nabla^2C_A+\dot N_A
\end{aligned}
$$



## Summary

In summary, the Convection Transfer Equations are:

$$
\left\{
\begin{aligned}
&\frac{\partial u}{\partial x} + \frac{\partial v}{\partial y} = 0 \\[2mm]

&\rho\left(u\frac{\partial u}{\partial x}+v\frac{\partial u}{\partial y}\right)
= -\frac{\partial p}{\partial x} + \mu \left(\frac{\partial^2u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2}\right) + X \\[2mm]

&\rho\left(v\frac{\partial v}{\partial x}+v\frac{\partial v}{\partial y}\right) = -\frac{\partial p}{\partial y} + \mu \left(\frac{\partial^2 v}{\partial x^2} + \frac{\partial^2 v}{\partial y^2}\right) + Y \\[2mm]

&\rho c_p \left( u \frac{\partial T}{\partial x} + v \frac{\partial T}{\partial y} \right) = k \left( \frac{\partial^2T}{\partial x^2} + \frac{\partial ^2 T}{\partial y ^2}  \right) - p \left(\frac{\partial u}{\partial x}  +\frac{\partial v}{\partial y} \right) + \mu \Phi + \dot q \\[2mm]

&\mu \Phi \equiv \mu \left\{
\left(\frac{\partial u}{\partial y} + \frac{\partial v}{\partial x}  \right)^2 + 2 \left[ \left( \frac{\partial u}{\partial x} \right)^2 + \left( \frac{\partial v}{\partial y} \right)^2 \right]- \frac 23 \left( \frac{\partial u}{\partial x} + \frac{\partial v}{\partial y}\right )^2
\right\}\\[2mm]

&u \frac{\partial C_A}{\partial x} + v \frac{\partial C_A}{\partial y} =  D_{AB}\left( \frac{\partial^2 C_A}{\partial x^2} + \frac{\partial^2 C_A}{\partial y^2} \right)+ \dot N_A
\end{aligned}\right.
$$


Or in vector form:

$$
\left\{
\begin{aligned}  
&\nabla \cdot \mathbf{u} = 0 \\[1mm]  
&\rho \left( \mathbf{u} \cdot \nabla \mathbf{u} \right) = -\nabla p + \mu \nabla^2 \mathbf{u} + \mathbf{f} \\[1mm]  
&\rho c_p \, \mathbf{u} \cdot \nabla T = k \nabla^2 T - p \, (\nabla \cdot \mathbf{u}) + \mu \Phi + \dot q \\[1mm]  
&\mu \Phi = \mu \left\{
\left(\frac{\partial u}{\partial y} + \frac{\partial v}{\partial x}  \right)^2 + 2 \left[ \left( \frac{\partial u}{\partial x} \right)^2 + \left( \frac{\partial v}{\partial y} \right)^2 \right]
\right\}\\[1mm]
&\mathbf u \cdot \nabla C_A = D_{AB}\nabla^2C_A+\dot N_A
\end{aligned}
\right.
$$

