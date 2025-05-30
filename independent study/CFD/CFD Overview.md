# CFD Overview


For an isotropic, incompressible fluid, the [Navier Stokes Equations](Navier%20Stokes%20Equations.md) are:

$$\rho \frac{\partial \textbf u}{\partial t}= -\nabla p+\mu \nabla ^2 \textbf u + \textbf f-\rho(\textbf u \cdot \nabla \textbf u)$$

> The term $\rho (\textbf u \cdot \nabla \textbf u)$ can be written as $\rho [(\textbf u \cdot \nabla)\textbf u]$ to show the directional derivative. 

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

For solving this equation, I have notes on [Poisson's equation](Poisson's%20equation.md). 

## Discretization 

### Python Notes

2D Vector fields in NumPy are usually of the shape `(2, H, W)` where H is the height and W is the width. Indexing is then done as:
```python
field = np.zeros((2, H, W))

field[0, 5, 10] # 0 means x-axis; 5 means y=5, and 10 means x=10
```

--- 
For evaluating the *divergence* $\nabla \cdot \textbf F$ , you can use:
```python

du_dy, du_dx = np.gradeint(field[0])
dv_dy, dv_dx = np.gradeint(field[1])

divF = du_dx + dv_dy

```

You do this because $\nabla \cdot F = \frac{\partial F_x}{\partial x} + \frac{\partial F_y}{\partial y}$ 


---

For evaluating the *laplacian* $\nabla ^2 \cdot \textbf F$ , you use:

```python
u, v = field

# first derivatives
du_dy, du_dx = np.gradient(u)
dv_dy, dv_dx = np.gradient(v)

# second derivatives
d2u_dy2, _    = np.gradient(du_dy)
_,    d2u_dx2 = np.gradient(du_dx)
d2v_dy2, _    = np.gradient(dv_dy)
_,    d2v_dx2 = np.gradient(dv_dx)

# form component Laplacians
lap_u = d2u_dx2 + d2u_dy2
lap_v = d2v_dx2 + d2v_dy2

laplacian = np.stack([lap_u, lap_v], axis=0)
```

The shape will be the same as the original field. A Laplacian is:

$$\nabla^2 \textbf F = \left(\nabla^2 u, \nabla^2v \right)$$

where $\textbf F$ is a vector field and $u$ and $v$ are scalar fields. For a scalar field:

$$\nabla ^2 f = \frac{\partial ^2 f}{\partial x^2}+\frac{\partial ^2 f}{\partial y ^2}$$
So, we first calculate $\partial ^2 u / \partial x^2$ and $\partial ^2 u / \partial y^2$ (along with the same for $v$), sum them to get $\nabla ^2 u$ and $\nabla ^2 v$, then stack the two fields to get the vector field laplacian. 

---

For something like $(\textbf u \cdot \nabla)\textbf u$ , realize that $(\textbf u \cdot \nabla)$ is a **directional-derivative operator** and is not the same as $(\nabla \cdot \textbf u)$. 

Mathematically (in 2D):

$$(\textbf u \cdot \nabla)\textbf F = u \frac{\partial \textbf F}{\partial x}+v \frac{\partial \textbf F}{\partial y}=\begin{bmatrix}
u (\partial F_x/\partial x)+v(\partial F_x/\partial y)\\
u (\partial F_y/\partial x)+ v(\partial F_y/\partial y)
\end{bmatrix}
$$

In the [Navier Stokes Equations](Navier%20Stokes%20Equations.md), $(\textbf u \cdot \nabla)\textbf u$ represents *advection*. Because $\textbf F = \textbf u$ in this case, you can represent this in Python with:

```python
u, v = field[0], field[1]

du_dy, du_dx = np.gradient(u)
dv_dy, dv_dx = np.gradient(v)

adv_u = u * du_dx + v * du_dy 
adv_v = u * dv_dx + v * dv_dy 

advection = np.stack([adv_u, adv_v]) 
```


