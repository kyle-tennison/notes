# Stress Elements

## Cartesian Shear Stress

"**Cross shears**" (those are, shears that cross each others paths) are always equal to one another *when the system is in equilibrium.* You can prove this relatively easily:

![|321x356](excalidraw-2026-01-19-20.30.11.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-01-19-20.30.11.excalidraw.md)%%

Assume the side length of this stress element it $dx$ such that the stresses do not vary significantly over the change in distance.

$$
\begin{aligned}
\sum M_A =0&= \left(\tau_{xy}\,dz\,dy\right)\left(\frac{dx}{2}\right) + \left(\tau_{xy}\,dz\,dy\right)\left(\frac{dx}{2}\right)-\left(\tau_{yx}\,dz\,dx\right)\left(\frac{dy}{2}\right)-\left(\tau_{yx}\,dz\,dx\right)\left(\frac{dy}{2}\right)\\\\
&=\left(\tau_{xy}\,dz\,dy\,dx\right) - \left(\tau_{yx}\,dz\,dy\,dx\right) \\\\
&=(\tau_{xy}-\tau_{yz})\,dx\,dy\,dz\\\\
&= \tau_{xy}-\tau_{yz} \quad \because dx\,dy\,dz \ne 0\\\\
\therefore \tau_{xy}&=\tau_{yz}
\end{aligned}$$

The same math can be applied to any of the *cross-shears*:

$$\tau_{xy}=\tau_{yx}\qquad \tau_{zy}=\tau_{yz}\qquad \tau_{xz}=\tau_{zx}$$
^cross-shear-equality

Hence, you can describe most stress elements with just six stresses. 


### Matrix Forms

In 3D matrix form, this is:

$$\boldsymbol{\sigma} = \begin{bmatrix}
\sigma_{xx} & \tau_{xy} & \tau_{xz} \\
\tau_{yx} & \sigma_{yy} & \tau_{yz} \\
\tau_{zx} & \tau_{zy} & \sigma_{zz}
\end{bmatrix}$$

![[image-88.png]]

In 2D form (covered more in [Plane Stress](#Plane%20Stress) below) it is:

$$\boldsymbol{\sigma} = \begin{bmatrix}
\sigma_{xx} & \tau_{xy} \\
\tau_{yx} & \sigma_{yy}
\end{bmatrix}$$

### Plane Stress

Often, stresses are simplifed into "2D," as shown in (b):

![[image-83.png]]

> From Shingley's p. 102

However, it is important to realize that *this is still a 3D element.* These "2D" elements are really just 3D elements under **plane stress**, where one of the surfaces has zero stress. In the above example, the element is still 3D, just $\sigma_{zz}, \tau_{zx}, \tau_{zy}$ are all zero. 

Plane stresses occur in thin flat parts loaded only perpendicularly. 

## Mohr's Circle for Plane Stress

![](excalidraw-2026-01-20-14.52.17.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-01-20-14.52.17.excalidraw.md)%%

If we define a vector $n$ that is at an angle $\phi$ to $x$ and slice the element as shown above, we will uncover new shear and normal stresses at our new cross section. 

Summing forces and adjusting for areas

$$\sigma = \frac{\sigma_x + \sigma_y}{2}+\frac{\sigma _x+\sigma_y}{2}\cos 2\phi + \tau_{xy}\sin 2 \phi \tag 1$$
^translated-normal
$$\tau = - \frac{\sigma_x - \sigma_y}{2} \sin 2 \phi + \tau_{xy}\cos 2\phi \tag 2$$
^translated-shear

These are the **plane-stress transformation equations**. 

Taking the derivative of Eq. 1 gives:
$$\tan2\phi_p = \frac{2 \tau_{xy}}{\sigma_x - \sigma_y} \tag 3$$
^principle-shear-direction

A quick note on this:

```python
x = sp.symbols('x')
sp.plot(sp.tan(x), (x, 0, 2*sp.pi), ylim=(-10,10), show=False, ylabel="$\\tan (x)$", title="Tangent $\\in [0, 2\\pi]$").save("media/ME-3180-demo3.png")
```

![|442x332](ME-3180-demo3.png)

If we set $\tan (x) = c$ where $c$ is any real number, we can define *two* values for x. By solving the above Eq. 3 for $\phi_p$, we can get two values:

1. One of these values contains the *maximum normal stress* $\large \sigma_1$
2. The other contains the *minimum normal stress* $\large \sigma_2$ 

And, the angle between the two will always be $90^\circ$. These are the **principle stresses** and $\phi_p$ are their **principle directions**. 

Something similar can be done for shear stresses. By taking the derivative of Eq. 2 with respect to $\phi$ gives:

$$\tan 2\phi_s = - \frac{\sigma_x-\sigma_y}{2\tau_{xy}} \tag 4$$
^shear-maxima-directions

where $\phi_s$ gives the angles where $\tau$ reaches its "extreme value". Both angles are again $90^\circ$ apart from each other. At both of these $\phi_s$ angles, the normal stress is:

$$\sigma= \frac{\sigma_x+\sigma_y}{2}$$

**The extreme-value is not necessarily the maximum.**

---

Notice that $\tan 2\phi_p$ and $\tan 2\phi_s$ are negative reciprocals. This means that the $2\phi_p$ and $2\phi_s$ angles are $90^\circ$ apart. This means that *the angle between the surfaces with the maximum shear stresses are ±45° to the surfaces with the principle stresses.*

---

Quantities for these principle stresses and "extreme-value" shear stresses are found with:

$$\sigma_1, \sigma_2 = \frac{\sigma _x + \sigma_y}{2} \pm \sqrt{\left( \frac{\sigma_x-\sigma_y}{2}\right)^2+\tau_{xy}^2}$$

and

$$\tau_1,\tau_ 2= \pm \sqrt{\left(\frac{\sigma_x-\sigma_y}{2}\right)^2+\tau^2_{xy}}$$

## Triaxial Stress

There is a 3D analog to the 2D "angle" where there is no shear stress: it is possible to take a stress element at a particular orientation such that it has no shear stress on any of its faces. Each face will have only principle normal stress, noted as $\sigma_1, \sigma_2, \sigma_3$, such that $\sigma_1 > \sigma_2 > \sigma_3$. 

You can use *Mohr's Circle for Triaxial Stesses* to find these by plotting,

![[image-86.png]]

Or, you can follow the [Eigenvalue Analysis for Principle Stress](4.%20Transformations.md#Eigenvalue%20Analysis%20for%20Principle%20Stress) from COE-3001. 

![[image-87.png]]

> Figure 2-5 in 8th edition. 

Kind of hard to interpret this graph, but the two axes are normal stress and shear stress. We can see where $\tau=0$, we have our principle stresses, and $\sigma_1$ is evidently the greatest, followed by $\sigma_2$ and then $\sigma_3$. 

We can see the values $\tau_{1/3}, \tau_{2/3}, \tau_{1/2}$; these are the *principle shear stresses.* Wording in the book is not 100% clear, but I believe the subscript of $\tau_{m/n}$ means that the shear stress acts at the 45° plane to the plane of $\sigma_m$ and $\sigma_n$. The (b) figure above shows for $m=1, n=2$. Again, not 100% sure.s

We can solve the values of the principle shear stresses relatively easily using geometry from Mohr's Circle:

$$\tau_{2/3} = \frac{\sigma_2-\sigma_3}{2}, \quad \tau_{1/3} = \frac{\sigma_1-\sigma_3}{2}, \quad \tau_{1/2}= \frac{\sigma_1-\sigma_2}{2}$$

and $\tau_{1/3}$ is obviously the biggest.

#### Detour: Trying to see if $\sigma_3$ is always negative (it's not)

We need a stress element that follows the [cross shear equality](#^cross-shear-equality) in 3D.

That is, we need values for:
$$\boldsymbol{\sigma} = \begin{bmatrix}
\sigma_{xx} & \tau_{xy} & \tau_{xz} \\
\tau_{yx} & \sigma_{yy} & \tau_{yz} \\
\tau_{zx} & \tau_{zy} & \sigma_{zz}
\end{bmatrix}$$

while sticking to this:

$$\tau_{xy}=\tau_{yx}\qquad \tau_{zy}=\tau_{yz}\qquad \tau_{xz}=\tau_{zx}$$
All this means really is that our stress tensor needs to be symmetric.

```python

import random
o_xx, o_yy, o_zz, t_xy, t_yz, t_xz = np.random.rand((6))

sigma = np.array([[o_xx, t_xy, t_xz],
                  [t_xy, o_yy, t_yz],
                  [t_xz, t_yz, o_zz]])
              
eigenvalues, eigenvectors = np.linalg.eig(sigma)

o1, o2, o3 = sorted(eigenvalues, reverse=True)
print(o1, o2, o3)
```

Playing with this shows that, despite the Mohr's Circle diagram, $\sigma_3$ isn't always negative. Also, $\sigma_2$ and $\sigma_1$ (?) aren't necessarily positive either. 

> Note: I actually can't find an instance where $\sigma_1$ is negative.



### Octahedral Stresses

![[image-89.png|310x332]]

Very difficult to picture in my opinion.

If you take a stress element, then slice it with a plane that forms equal angles to each of the 3 principle stresses, then analyze the stresses on that plane, you will see the *octahedral stresses.*

This allows you to represent all of the principle stresses with two numbers, $\tau_{\rm oct}$ and $\sigma_{\rm oct}$. 

There are a few different ways to calculate these, depending on which values you have:

$$\begin{aligned}
\tau_{\rm oct} &= \frac 23 \left(\tau_{1/2}^2+\tau_{2/3}^2+\tau_{1/3}^2\right)^{1/2}\\
&=\frac 13\left[ (\sigma_1 - \sigma_2)^2 + (\sigma_2-\sigma_3)^2+(\sigma_3-\sigma_1)^2 \right]^{1/2}\\
&= \frac 13 \left[(\sigma_x-\sigma_y)^2+(\sigma_y-\sigma_z)^2+(\sigma_z-\sigma_x)^2+6(\tau_{xy}^2+\tau_{xz}^2+\tau_{yz}^2) \right]^{1/2}\\\\
\sigma_{\rm oct} &= \frac 13(\sigma_1+\sigma_2+\sigma_3)\\
&=\frac 13(\sigma_x+\sigma_y+\sigma_z)
\end{aligned}
$$

These values are sometimes used in evaluating a part for failure. 