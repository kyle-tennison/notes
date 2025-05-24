# CFD Overview


For an isotropic, incompressible fluid, the [Navier Stokes Equations](Navier%20Stokes%20Equations.md) are:

$$\rho \frac{\partial \textbf u}{\partial t}= -\nabla p+\mu \nabla ^2 \textbf u + \textbf f-\rho(\textbf u \cdot \nabla \textbf u)$$

### Solving the Pressure Gradient

To solve this equation, you first need to find $\nabla p$, which is the pressure gradient. You can do this using a [Shooting Method](Ordinary%20Differential%20Equations.md#^9586fd) along with a predictor-corrector method to approximate $\nabla p$. 


The [Incompressible Pressure Poisson](Navier%20Stokes%20Equations.md#Incompressible%20Pressure%20Poisson) equation is:

$$\nabla^2 p = -\rho \nabla \cdot(\textbf u \cdot \nabla \textbf u) + \nabla \textbf f$$

To solve this, we project an *intermediate* velocity $\textbf u^*$ that would be the *velocity with neglected pressure.* You can find this by discretizing the Navier Stokes Equation without the $- \nabla p$ term:

$$\rho \frac{\textbf u^*-\textbf u_i}{\Delta t}=\mu \nabla^2\textbf u_i+\textbf f_i- \rho(\textbf u_i \cdot \nabla \textbf u_i)$$

Rearranged for $\textbf u^*$, this is:

$$\textbf u^*=\textbf u_i+\frac{\Delta t}{\rho}\left(\mu \nabla^2\textbf u_i+\textbf f_i- \rho(\textbf u_i \cdot \nabla \textbf u_i)\right)$$

At this point, the divergence $\nabla \cdot \textbf u^* \ne 0$ (usually). So, then we *correct* $\textbf u^*$ by some pressure to get the corrected $\textbf u_{i+1}$:

$$\textbf u_{i+1}=\textbf u^*+\frac{\Delta t}{\rho}\left(-\nabla p_{i+1}\right)$$

What we are doing here is adding back the previously omitted pressure term (that we currently don't know). Now, we can enforce the condition that $\nabla \cdot \textbf u _{i+1}=0$. We get this by taking the divergence of both sides of the equation above:

$$
\begin{aligned}
0=\nabla \cdot \textbf u_{i+1}&=\nabla\cdot \left[ \textbf u ^*+\frac{\Delta t}{\rho}(-\nabla p_{i+1})\right]\\

&=\nabla\cdot \textbf u^*- \frac{\Delta t}{\rho}\nabla^2p_{i+1}\\

\nabla^2p_{i+1}&=\frac{\rho}{\Delta t}\nabla \cdot \textbf u^*

\end{aligned}
$$



