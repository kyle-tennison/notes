#  Galileo's Relativity Principle

Chapter 1.3 of [Landu-Lifshitz Course on Mechanics](Landu-Lifshitz%20Course%20on%20Mechanics.md)

## Reference Frames

When choosing a reference frame, we need to be careful. If we choose an arbitrary reference frame, space *may appear inhomogeneous and anisotropic*. A non-inertial reference frame, like someone on a merry-go-round, would experience these phenomena. In one of these frames, a body at rest would not remain at rest. If we get more abstract, these reference frames may also have *inhomogeneous time*, which would further complicate things.

Instead, we will look at **inertial reference frames**. In these frames, we ensure that *space is homogeneous and isotropic and time is homogeneous.* In this frame, a body at rest will indeed remain at rest.

Landu claims that:

> "It is found ... that a frame of reference can always be chosen in which space is homogeneous and isotropic and time is homogenous."

In other words, **there is always an inertial reference frame**. 

---

In classical mechanics, this *homogeneity of space* implies that the *lagrangian should not depend specifically on the position in space*; the laws of physics apply the same at all locations in space. Similarly, the *homogeneity of time* implies that the *lagrangian is independent of time*; the laws of physics remain constant with time.

Landu also asserts that space is isotropic, which, in turn, means that the *lagrangian must be independent of the **direction** of velocity* in an inertial frame—it is only dependent on the magnitude. For reasons that exceed my understanding, $|\textbf v|^2$ is used in place of $|\textbf v|$, which seems to simplify calculations later on. Mathematically, no information is lost in this transformation.

We can express these inertial frame properties by saying that:

$$L = L(v^2) \tag 1$$
^eq-1
meaning that the lagrangian is only dependent on the magnitude of velocity $v^2 = \textbf v \cdot \textbf v$.

Now, if we look at [Euler-Lagrange equation](Lagrange's%20Equations.md#^eq-7), remove the ${\partial L}/{\partial q}$ term because, now that the lagrangian is independent of $q$, shown in [eq. 1](#^eq-1), this value is zero. The reduced equation becomes:

$$\frac{d}{dt}(\frac{\partial L}{\partial \textbf v})=0 \tag 2$$




## Lagrangian for a Free Particle

Say we have two *inertial* reference frames $L$ and $L'$, one moving ever so slightly faster than the other by $\epsilon$. We can say that $v' = v+\epsilon$ . Using this, we can say:

$$L(v^2)=L(v'^2)=L(v^2+2\mathbf v\cdot \epsilon + \epsilon ^2) \tag 3$$
^eq-5
Then, we can expand this using a **Taylor series expansion**. We get:

$$L(v'^2)=L(v^2)+\frac{\partial L}{\partial v^2}\cdot \Delta + \text{Higher Order Terms}  \tag4$$
^eq-4
Remember, a Taylor series expansion looks like:

$$f(x)=f(a)+f'(a)(x-a)+\text{Higher Order Terms}$$

This $∆$ will be the equivalent of $x-a$, which, in this case, is $v^2-v'^2$.

$$\Delta = v^2-v'^2=v^2+2\textbf v \cdot \epsilon + \epsilon ^2 \tag 5$$

If we substitute the expression for $\Delta$ into [eq. 4](#^eq-4), *and neglect higher order terms* we get:

$$L(v'^2) =L(v^2)+\frac{\partial L}{\partial v^2}(2\textbf v \cdot \epsilon+\epsilon^2) \tag 6$$

Because $\epsilon$ is a small (infinitesimal), we can neglect the term $\epsilon ^2$ and reduce the equation to:

$$L(v'^2) =L(v^2)+\frac{\partial L}{\partial v^2}2\textbf v \cdot \epsilon \tag 7$$

Now, we know, from Galilean relativity, that these two Lagrangians, both of inertial reference frames, will have equivalent equations of motion. Therefore, they must vary *only* by a total time derivative of a function of position and time, by [Lagrange's Equations eq. 9](Lagrange's%20Equations.md#^eq-9). Because $\textbf v$ is already in the term, we know that $\partial L / \partial v^2$ must be independent of $v$. 

We know that $\frac{\partial L}{\partial v^2}$ is independent of v, and is therefore a constant. Let us assign the arbitrary constant $c=\frac{\partial L}{\partial v^2}$. Now, if we integrate over $\frac{\partial L}{\partial v^2}$ with respect to $v^2$, we can get $L$:

$$L = \int c\ d(v^2) = cv^2+C$$

From experiment, we know $c=\frac{m}{2}$, where $m$ is mass. $C$ drops off, and we get:

$$L = \frac{1}{2}mv^2 \tag 8$$

We can expand this for *a collection of particles* that **do not interact** to say:

$$L = \sum_i \frac{1}{2} m_iv_i^2 \tag 9$$
^eq-9

Because $v^2 = \frac{dl^2}{dt^2}$ , we can say:

$$L = \frac{1}{2}(\dot x^2 + \dot y ^2 + \dot z^2) \tag {10}$$

> The book references more expansions on pg. 8 for cylindrical and spherical coordinates.


## Lagrangian for a System of Particles

In a **closed system**, particles *can interact* with each other, but no other bodies. If we take the independent-particle in [eq. 9](#^eq-9) Lagrangian and modify it by a function $U$ of the coordinates that varies depending on the nature of the interaction, we can generically express the lagrangian of a closed system as:

$$L = \sum _i \frac12 m_i \textbf v_i^2-U(\textbf r_1, \textbf r_2, \dots) \tag{11}$$

From this, we can extract $T=\frac12m\textbf v^2$ and call it **kinetic energy**. We also call $U$ the **potential energy** of the system.

The fact that $U$ is independent of time reveals the nature of *instantaneous propagation* in classical mechanics. You can dive deep into this, but if the potential energy also depended on time, i.e if its propagation to other particles was not instantaneous, then not all frames would have the same equations of motion and Galileo's Relativity Principle would be invalidated. This is a key assumption in classical mechanics.


