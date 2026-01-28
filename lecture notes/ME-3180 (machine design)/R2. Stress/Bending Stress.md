# Bending Stress


## Derivation

We can derive some of the bending equations by first looking at pure bending when there is no shear, then using superposition to apply it to more complex scenarios.

![](excalidraw-2026-01-26-19.31.32.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-01-26-19.31.32.excalidraw.md)%%

> There is a lot going on here; only pay attention to $d\phi$, $b'\text{ - }c'$, $b\text{ - }c$, and $\rho$. 

Look at the line segment $b'\text{ - }c'$; this would be orthogonal to the longitudinal axis of the beam before it bent. Now, it has changed to $b\text{ - }c$ by rotating by an angle $d\phi$. 

Let's look at a small part of the neutral axis $ds$ which is the one "fiber" of the beam that does not change length. By looking at how much the angle $\phi$ changes over some infinitesimal length $ds$, we can find the *radius of curvature* $\rho$. 


![](excalidraw-2026-01-26-19.35.28.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-01-26-19.35.28.excalidraw.md)%%


Simple trig shows that $\rho \sin(d \phi) = ds$, but because $d\phi \sim 0$, we can use the [Small Angle Approximation](Small%20Angle%20Approximation.md) to instead say:

$$\rho\, d\phi = ds, \qquad \text{or} \qquad \frac{1}{\rho} = \frac{d\phi}{ds}$$


![](excalidraw-2026-01-26-19.44.57.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-01-26-19.44.57.excalidraw.md)%%


Then, we know that the change in length $dx$ can be related with to $d\phi$ with:

$$dx = y \sin(d\phi) \approx y \,d\phi$$

Where y is importantly defined in the *cross section*, with $y=0$ sitting on the neutral axis (dotted line above).

The change in "fiber length" from an infinitesimal chunk will change from a constant $ds$ across the $y$ axis of the cross section, to $ds-dx=ds- y\,d\phi$. So, using the formula:

$$\epsilon = \frac{\Delta L}{L} = -\frac{dx}{ds} = -\frac{y\,\cancel{d\phi}}{\rho\,\cancel{d\phi}} = -\frac{y}{\rho}$$

And, assuming deformation is linear-elastic, $\epsilon = \sigma E$. Thus, multiplying both sides by $E$ gives:

$$\sigma = -\frac{Ey}{\rho}$$
^governoring-bending-stress-eq

Now, because bending is an internal stress, its forces need to sum to zero.

$$\int\sigma\,dA = -\frac{E}{\rho} \int y \,dA = 0$$

Which forces us to define $y$ at the neutral axis, giving us a concrete definition of the neutral axis.

The moments need to also cancel out, but we need to remember that there *is an external bending moment* $M$ to consider:
Summing moments gives:

$$M= \int \sigma y \, dA = - \frac E \rho \int y^2 \, dA = - \frac {EI}{\rho}$$

where $I$ is the second moment of area. Rearranging this gives an equation that can be used to calculate beam deformations:

$$\boxed{{\frac{1}{\rho}} = \frac{M}{EI}}$$
^radius-of-curvature-bending-eq

If you substitute this expression for $\rho^{-1}$ into $\sigma = -{Ey}{\rho^{-1}}$ you get:

$$\sigma = -Ey \frac{M}{EI} = \boxed{- \frac{My}{I} }$$

which is the famous bending equation.


## Normal Stress from Bending

Much of this is covered in [Normal Stresses in Beams](3.%20Beams.md#Normal%20Stresses%20in%20Beams). The main highlight is that:

$$\boxed{\sigma = -\frac{My}{I}}$$

where $y$ is the distance from the neutral axis ($y=0$). The stress will be positive if in tension, and negative if in compression. For *positive* bending ($M>0$), looking at the *top* of the bar ($y>0$), we expect the stress to be in compression ($\sigma < 0$). This is why **the negative sign is important.**



A lot of the time, the sign is omitted and the equation is written as:

$$\sigma= \frac{Mc}{I}$$

where $c=y_{\max}$. This gives the *magnitude* of the maximum stress, but lacks the sign. Something to beware of.

## Asymmetrical Cross-Sectioned Beams

![](excalidraw-2026-01-26-20.14.14.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-01-26-20.14.14.excalidraw.md)%%

If the cross section is still normal, but the neutral axis is still orthogonal to the cross section, the formula [above](#^governoring-bending-stress-eq) ($\sigma = -Ey/\rho$) remains valid. To arrive at $\sigma = -My/I$ we asserted that the moment $M_z$ about the neutral axis was zero. However, we need to now enforce that $M_y$ is zero at all points too by enforcing:

$$M_y = \int\sigma z\,dA = -\frac E \rho \int yz\,dA$$

This integral $\int yz\,dA=I_{yz}$ , which is zero for when things are symmetric. 

This still seems hard to solve, but it gives you another necessary constraint to consider. 

## Transverse Shear Stress

![](excalidraw-2026-01-26-20.34.55.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-01-26-20.34.55.excalidraw.md)%%

Transverse shear stress is shear stress that occurs from bending *when there is shear applied on the beam*. Better put, **transverse shear stress occurs from the *change in* bending.*** 

Across some infinitesimal $dx$, the bending moment changes by $dM$. The force on the left-hand side of the removed block is $\sigma\cdot dA$ , and the force on the right-hand side is $(\sigma + d \sigma) \cdot dA$. This means that there is a $d\sigma \cdot dA$ *force imbalance* caused by the difference in normal bending stress. The only way to account for this is for there to be some shear stress, shown as $\tau$. 


Summing forces, we get:

$$
\begin{aligned}
\sum F_x &= \sigma\cdot dA - (\sigma + d\sigma)\cdot dA + \tau\cdot dA' \\
& = -d\sigma \cdot dA + \tau \cdot dA' \\
&= \frac{dM\,y}{I}\,dA + \tau \cdot dA' \\
&= \frac{dM}{I} \int _0^{y_{\rm max}} y\,dA + \tau\,b\, dx\ \\
\tau &= \frac{dM}{dx}\frac{1}{I\cdot b} \int _0^{y_\max} y\,dA\\
\end{aligned}$$



$$\boxed{\tau = \frac{VQ}{Ib}}$$

because $V = dM/dX$ and $Q = \int_0^{y_\max} y\,dA$. Remember that $b$ is a function of $y$; the $z$ thickness of the chunk will likely change over $y$. 


However, it is usually easiest to consult this table

![[image-92.png]]


## Torsion

Much of this is covered in [Torsion Bar](2.%20Torsion%20Bar.md). 

The angle of twist for a solid round bar is:

$$\theta = \frac{Tl}{GJ}$$

where $T$ is torque, $l$ is length, $G$ is the shear modulus, and $J$ is the polar moment of inertia. 

The torsion from torque is:

$$\boxed{\tau_\max = \frac {Tr}{J}}$$

where $r$ is the radius from the center. 

