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

Say we have two *inertial* reference frames $L$ and $L'$, one moving ever so slightly faster than the other by $\epsilon$. We can say that $v' = v+\epsilon$ . 

