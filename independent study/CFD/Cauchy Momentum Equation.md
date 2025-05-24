# Cauchy Momentum Equation

The **Cauchy Momentum Equation**, which is:

$$\frac{D\textbf{u}}{Dt}=\frac{1}{\rho }\nabla \cdot \boldsymbol{\sigma}+\textbf{f}$$

where $u$ is the velocity vector field, $t$ is time, $D \textbf{u}/Dt$ is the [Material Derivative](Material%20Derivatives.md) of the material element, $\rho$ is the density at the given point in the media, $\boldsymbol{\sigma}$ is the [Stress Tensor](Stress%20Tensors.md), and: $f = \begin{bmatrix}f_x\\f_y\\f_z\end{bmatrix}$ . 


The quantity $\nabla \cdot \boldsymbol{\sigma}$ is the [Divergence of the Stress Tensor](Stress%20Tensors.md#^divergence-of-stress-tensor). 

This equation describes *non-relativistic momentum transport in any continuum*. 

## Derivation

From [Newton's Second Law](Galileo's%20Relativity%20Principle.md#^newtons-second-law), we know:

$$\textbf{F}=m\boldsymbol{\ddot x}$$

And, from the [Conservation of Momentum](Conservation%20Laws.md#Momentum), we know:

$$\textbf {p} = m \boldsymbol{\dot x}$$
Hence, the time derivative of momentum is:

$$\boldsymbol{\dot p} = m \boldsymbol{\ddot x}$$

So it can be said that **Force is the first time-derivative of Momentum**; that is:

$$\textbf{F} = \boldsymbol{\dot p}$$

We then split $\textbf{F}$ into forces on the body $\textbf{F}_m$ and forces on the surface $\textbf{F}_p$ so that $\textbf{F}=\textbf{F}_m+\textbf{F}_p$ 

Then, by looking at the [Stress Tensor](Stress%20Tensors.md) (and accounting for stress variations over its volume), we can sum the surface forces in the different axes. The forces for the x-axis are shown here (explanation provided in [Directional Forces](Stress%20Tensors.md#Directional%20Forces)).

![[image-27.png]]
 
This gives us:

$$
\textbf{F}_p =\begin{bmatrix}

\frac{\partial\sigma_{xx}}{\partial_x}dxdydz+\frac{\partial \sigma_{yx}}{\partial y}dydxdz+\frac{\partial \sigma_{zx}}{\partial z}dzdxdy\\

\frac{\partial\sigma_{xy}}{\partial_x}dxdydz+\frac{\partial \sigma_{yy}}{\partial y}dydxdz+\frac{\partial \sigma_{zy}}{\partial z}dzdxdy\\

\frac{\partial\sigma_{xz}}{\partial_x}dxdydz+\frac{\partial \sigma_{yz}}{\partial y}dydxdz+\frac{\partial \sigma_{zz}}{\partial z}dzdxdy\\

\end{bmatrix}$$


In differential form, this can be expressed as $\textbf{F}_p=(\nabla \cdot \boldsymbol{\sigma})dxdydz$. 

Then, the body forces ($\textbf{F}_m$) can be expressed as:

$$\textbf{F}_m=\textbf{f}\rho\;dxdydz$$ 
where $\textbf{f}$ is an acceleration field.

Now, if we put this into the $\textbf{F}=\boldsymbol{\dot p}$  balance, we get:

$$\boldsymbol{\dot p}=(\nabla\cdot \boldsymbol{\sigma})dzdydz+\textbf{f}\rho dxdydz$$

We can further reduce this by saying that:

$$\textbf{p}=\textbf{u}m=\textbf{u}\rho \;dxdydz$$
(where $\textbf{u}$ is velocity)

such that:

$$\boldsymbol{\dot p }=\boldsymbol{\dot u}\rho\;dxdydz$$

Now, the governing $\textbf{F}=\boldsymbol{\dot p}$ becomes:

$$\boldsymbol{\dot u}\rho\;dxdydz=(\nabla \cdot \boldsymbol{\sigma})dx dy dz + \boldsymbol{f}\rho\; dz dy dz$$

which, upon dividing both sides by $dxdydz$, reduces to:

$$\boldsymbol{\dot u}\rho = (\nabla\cdot \boldsymbol{\sigma})+\boldsymbol{f}\rho \Rightarrow \boldsymbol{\dot u}=\frac{1}{\rho}\nabla\cdot \boldsymbol{\sigma}+\textbf{f}$$

If we say that $\boldsymbol {\dot u}$ contains both the local change and global change (i.e., it is a [Material Derivative](Material%20Derivatives.md)), we can say:

$$\underbrace{\frac{D\textbf{u}}{Dt}=\frac{1}{\rho}\nabla\cdot\boldsymbol{\sigma}+\textbf{f}}_{\text{Definition}}$$


#### Intuition

Effectively, we've just summed surface and body forces together, then expressed it as a change in momentum/velocity.


## Conservation form

By setting the stress tensor $\boldsymbol{\sigma}$ as the sum of a viscosity term $\boldsymbol{\tau}$ (i.e. the [Deviatoric Stress](Stress%20Tensors.md#^e76ff6)) and a pressure term $-p \textbf{I}$ (volumetric/hydrostatic stress), the equation expands to:

$$

\begin{aligned}
\frac{D\textbf{u}}{Dt} 
&= \frac{1}{\rho} \nabla \cdot (-p\textbf{I} + \boldsymbol{\tau}) + \textbf{f} \\
&= \frac{1}{\rho} \left( \nabla \cdot (-p\textbf{I}) + \nabla \cdot \boldsymbol{\tau} \right) + \textbf{f} \\
&= \frac{1}{\rho} \left( -\nabla p + \nabla \cdot \boldsymbol{\tau} \right) + \textbf{f}\\

\rho \frac{D\textbf{u}}{Dt}  &=-\nabla p + \nabla \cdot \boldsymbol{\tau}+\rho\textbf{f}

\end{aligned} \\
$$

If the material derivative is expanded, this becomes:

$$\underbrace{\rho(\frac{\partial \textbf{u}}{\partial t})+\rho (\textbf{u}\cdot \nabla)\textbf{u}=-\nabla p+\nabla \cdot \boldsymbol \tau + \rho \textbf a}_{\text{Momentum Equation}}$$
^momentum-equation

---

Leaving this here for now, if we define mass as:

$$m = \iiint\limits_V\rho(\textbf{x},t)dV$$

then take the Material time derivative:

$$

\begin{aligned}
\frac{Dm}{Dt}&=\frac{D}{Dt} \iiint \limits \rho(\textbf{x}, t)dV\\
&=\iiint\limits_V\left(\frac{\partial \rho}{\partial t} + \textbf{u} \cdot \nabla \rho \right)dV=\iiint\limits_V\left(\frac{\partial \rho}{\partial t} + \nabla(p\textbf{u})\right)dV\\
&=\iiint\limits_V\left(\underbrace{\frac{\partial \rho}{\partial t} + \nabla(p)\cdot \textbf{u}}_{D \rho /D\textbf{u}}+p(\nabla \cdot \textbf{u})   \right) dV\\
&=\iiint_V\frac{D \rho}{Dt}+p(\nabla \cdot \textbf{u})dV = 0 \text{\;(Because mass is conserved)}

\end{aligned}
$$


This means that we can take this expression out of the integral because it equals zero, giving:

$$0=\frac{D\rho}{Dt}+p(\nabla \cdot \textbf{u})$$

This can be expressed as well simply as:

$$\underbrace{0=\frac{\partial \rho}{\partial t} + \nabla \cdot ( \rho \textbf{u})}_{\text{Continuity Equation}}$$
^continuity-equation
> This is evident from the derivation above

This is often called the **Continuity Equation**, which is really just the conservation of mass.

In the case that the fluid is incompressible, $D \rho / D t = 0$ and the equation reduces to $\nabla \cdot \textbf u =0$. 

---

Going back to the momentum equation:

$$\rho(\frac{\partial \textbf{u}}{\partial t})+\rho (\textbf{u}\cdot \nabla)\textbf{u}=-\nabla p+\nabla \cdot \boldsymbol \tau + \rho \textbf a$$

Notice that the term $\rho \left(\frac{\partial \textbf u}{\partial t}\right)$ can be expressed as:

$$\rho \left( \frac{\partial \textbf u}{\partial t} \right) = \frac{\partial (\rho \textbf u)}{\partial t} - \frac{\partial p}{\partial t}\textbf u$$
This expression comes from the chain rule being applied to $\partial (p \textbf u) / \partial t$:

$$\frac{\partial(p\textbf u)}{\partial t}=\frac{\partial p}{\partial t}\textbf u + \rho \frac{\partial \textbf u }{\partial t}$$

Substituting this new expression for $\rho \left(\frac{\partial \textbf u}{\partial t}\right)$ into the momentum equation gives:

$$\left(\frac{\partial (\rho \textbf u)}{\partial t} - \frac{\partial p}{\partial t}\textbf u \right)+\rho (\textbf{u}\cdot \nabla)\textbf{u}=-\nabla p+\nabla \cdot \boldsymbol \tau + \rho \textbf a$$

Then, the Continuity equation gives the property that:

$$\frac{\partial \rho}{\partial t}=-\nabla\cdot(\rho \textbf u)$$

Substituting this into the the above equation yields:

$$\left(\frac{\partial (\rho \textbf u)}{\partial t} - \left(-\nabla\cdot(\rho \textbf u)\right)\textbf u \right)+\rho (\textbf{u}\cdot \nabla)\textbf{u}=-\nabla p+\nabla \cdot \boldsymbol \tau + \rho \textbf a$$
^1

Which simplifies to:

$$\frac{\partial (\rho \textbf u)}{\partial t}+(\nabla\cdot(\rho \textbf u)) \textbf u+\rho(\textbf u\cdot \nabla )\textbf u=-\nabla p + \nabla \cdot \boldsymbol \tau + \rho \textbf a$$

To clean up this notation, we can use the $\otimes$ operator:

The $\otimes$ operator represents a tensor product: $a \otimes b = ab^T$ if a and b are column vectors. The product is a tensor. 

This allows us to express:

$$(\nabla \cdot (\rho \textbf u))\textbf u+\rho(\textbf u \cdot \nabla)\textbf u = \nabla\cdot(\rho \textbf u \otimes \textbf u)$$
This cleans up the expression to become:

$$\underbrace{\frac{\partial (\rho \textbf u)}{\partial t}+\nabla\cdot(\rho \textbf u \otimes \textbf u)=-\nabla p + \nabla \cdot \boldsymbol \tau + \rho \textbf a}_{\text{Cauchy Momentum Equation (Conservation Form)}}$$

### Newton's Law Form

Re-expanding the conservation form of the equation above gives:

$$\textbf u\left( \frac{\partial p}{\partial t}+ \nabla \cdot (\rho \textbf u) \right)+\rho\left(\frac{\partial \textbf u}{\partial t}+\textbf u \cdot \nabla \textbf u \right)=-\nabla p+\nabla \cdot \boldsymbol \tau +\rho \textbf a$$

The term $\frac{\partial p}{\partial t}+ \nabla \cdot (\rho \textbf u)$ , by mass continuity, is equal to zero, meaning the equation can reduce to:

$$\rho\left(\frac{\partial \textbf u}{\partial t}+\textbf u \cdot \nabla \textbf u \right)=-\nabla p+\nabla \cdot \boldsymbol \tau +\rho \textbf a=\rho \frac{D\textbf u}{Dt}$$

We can bring back the material derivative into this equation to see how everything ties together. Then, if we let $\textbf s = -\nabla p+\nabla \cdot \boldsymbol \tau +\rho \textbf a$, we can then say:

$$\rho \frac{D \textbf u}{Dt}=\rho\left(\frac{\partial \textbf u}{\partial t}+\textbf u \cdot \nabla \textbf u\right)=s$$

In this form, we are really just expressing Newton's second law $F=ma$ in terms of body forces. You can also reach this conclusion with:

![[image-29.png]]







## Convective Acceleration

Convective Acceleration is the *time-independent acceleration of a flow with respect to space.*

![[image-28.png]]


The accelearation is nonlinear and represented with the quantity $\textbf u \cdot \nabla \textbf u$ .



## References

https://en.wikipedia.org/wiki/Cauchy_momentum_equation

