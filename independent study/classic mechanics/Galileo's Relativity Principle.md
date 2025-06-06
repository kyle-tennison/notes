#  Galileo's Relativity Principle

Chapter 1.3 of [Landu-Lifshitz Course on Mechanics](Landu-Lifshitz%20Course%20on%20Mechanics.md)

## Reference Frames

When choosing a reference frame, we need to be careful. If we choose an arbitrary reference frame, space *may appear inhomogeneous and anisotropic*. A non-inertial reference frame, like someone on a merry-go-round, would experience these phenomena. In one of these frames, a body at rest would not remain at rest. If we get more abstract, these reference frames may also have *inhomogeneous time*, which would further complicate things.

The Lagrangian yields equations of motion for a system. For a free particle, the equation of motion is simply Newton's second law. So, we can imagine that if space and time were inhomogeneous and the Lagrangian depended specifically on their quantities, then the *equations of motion for the system* would change depending on time and position. If Newton's second law only applied on Thursday afternoons in northeastern Spain, then we'd be dealing with this inhomogeneity.

Instead, we will look at **inertial reference frames**. In these frames, we ensure that *space is homogeneous and isotropic and time is homogeneous.* In this frame, a body at rest will indeed remain at rest.

Landu claims that:

> "It is found ... that a frame of reference can always be chosen in which space is homogeneous and isotropic and time is homogeneous."

In other words, **there is always an inertial reference frame**.

---

In classical mechanics, this *homogeneity of space* implies that the *Lagrangian should not depend specifically on the position in space*; the laws of physics apply the same at all locations in space. Similarly, the *homogeneity of time* implies that the *Lagrangian is independent of time*; the laws of physics remain constant with time.

To unravel this logic a bit further, homogeneity means all quantities are created equal. Imagine an infinitely flat plane; there is no beginning or end—everything is the same. Therefore, if we're dealing with homogeneous quantities, **there is no absolute quantity**; there are only differences between relative quantities. The place that we choose to reference either space or time from is entirely arbitrary; $t_0$ and $x_0$ can be set to any value—whichever is convenient for the system at hand.
^no-absolutes

Landu also asserts that space is isotropic, which, in turn, means that the *Lagrangian must be independent of the **direction** of velocity* in an inertial frame—it is only dependent on the magnitude. For reasons that exceed my understanding, $|\textbf v|^2$ is used in place of $|\textbf v|$, which seems to simplify calculations later on. Mathematically, no information is lost in this transformation.

We can express these inertial frame properties by saying that:

$$L = L(v^2) \tag 1$$
^eq-1

meaning that the Lagrangian is only dependent on the magnitude of velocity $v^2 = \textbf v \cdot \textbf v$.

Now, if we look at [Euler-Lagrange equation](Lagrange's%20Equations.md#^eq-7), we remove the ${\partial L}/{\partial q}$ term because, now that the Lagrangian is independent of $q$, as shown in [eq. 1](#^eq-1), this term is zero. The reduced equation becomes:

$$\frac{d}{dt}\Big(\frac{\partial L}{\partial \textbf v}\Big)=0 \tag 2$$

## Lagrangian for a Free Particle

Say we have two *inertial* reference frames $L$ and $L'$, one moving ever so slightly faster than the other by $\epsilon$. We can say that $v' = v+\epsilon$. Using this, we can write:

$$L' = L(v'^2) = L(v^2+2\mathbf v\cdot \epsilon + \epsilon^2) \tag 3$$
^eq-5

Then, we can expand this using a **Taylor series expansion**. We get:

$$L(v'^2)=L(v^2)+\frac{\partial L}{\partial v^2}\cdot \Delta + \text{Higher Order Terms}  \tag4$$
^eq-4

Remember, a Taylor series expansion looks like:

$$f(x)=f(a)+f'(a)(x-a)+\text{Higher Order Terms}$$

Here, $\Delta$ is the equivalent of $x-a$. In this case, $x=v'^2$ and $a=v^2$:

$$\Delta = v'^2-v^2=(v^2+2\textbf v\cdot \epsilon + \epsilon^2)-v^2 = 2 \textbf v\cdot \epsilon + \epsilon^2 \tag 5$$

If we substitute the expression for $\Delta$ into [eq. 4](#^eq-4), *and neglect higher order terms*, we get:

$$L(v'^2) = L(v^2)+\frac{\partial L}{\partial v^2}(2\textbf v \cdot \epsilon+\epsilon^2) \tag 6$$

Because $\epsilon$ is small (an infinitesimal), we can neglect the term $\epsilon^2$ and reduce the equation to:

$$L(v'^2) = L(v^2)+\frac{\partial L}{\partial v^2} \, 2\textbf v \cdot \epsilon \tag 7$$

Now, we know from Galilean relativity that these two Lagrangians, both corresponding to inertial reference frames, will have equivalent equations of motion. Therefore, they must vary *only* by a total time derivative of a function of position and time, according to [Lagrange's Equations eq. 9](Lagrange's%20Equations.md#^eq-9). See [Varied Lagrangians](Lagrange's%20Equations.md#Varied%20Lagrangians) for more info. Because $\textbf v$ is already in the term, we know that $\frac{\partial L}{\partial v^2}$ must be independent of $v$.

We know that $\frac{\partial L}{\partial v^2}$ is independent of $v$, and is therefore a constant. Let us assign the arbitrary constant $c=\frac{\partial L}{\partial v^2}$. Now, if we integrate $\frac{\partial L}{\partial v^2}$ with respect to $v^2$, we obtain $L$:

$$L = \int c\ d(v^2) = cv^2+C$$

From experiment, we know $c=\frac{m}{2}$, where $m$ is the mass. $C$ drops off, and we get:

$$\frac{1}{2}mv^2$$
> I don't know how this got here ^

We can expand this for *a collection of particles* that **do not interact** to write:

$$L = \sum_i \frac{1}{2} m_i v_i^2 \tag 9$$
^eq-9

Because $v^2 = \frac{dl^2}{dt^2}$, we can write:

$$L = \frac{1}{2}(\dot x^2 + \dot y^2 + \dot z^2) \tag {10}$$

> The book references more expansions on pg. 8 for cylindrical and spherical coordinates.

If we look back at $L'$, we notice that:

$$L' = \frac{1}{2}mv'^2 = \frac{1}{2}(v^2+2v\epsilon) = \frac{1}{2}mv^2+mv\epsilon$$

Because $mv\epsilon$ is linear in $v$, it is a total time derivative and hence does not influence the equations of motion.

## Lagrangian for a System of Particles

In a **closed system**, particles can interact with each other, but with no external bodies. If we take the independent-particle Lagrangian in [eq. 9](#^eq-9) and modify it by a function $U$ of the coordinates that varies depending on the nature of the interaction, we can generically express the Lagrangian of a closed system as:

$$L = \sum_i \frac12 m_i \textbf v_i^2 - U(\textbf r_1, \textbf r_2, \dots) \tag{11}$$
^eq-11

From this, we can extract $T=\frac12m\textbf v^2$ and call it **kinetic energy**. We also call $U$ the **potential energy** of the system. Using these terms, we can write the Lagrangian as:

$$L = \sum_i T(q_i, \dot q_i) - U(q_i) \tag{11a}$$
^eq-11a

The fact that $U$ is independent of time reveals the nature of *instantaneous propagation* in classical mechanics. You can dive deep into this, but if the potential energy also depended on time, i.e., if its propagation to other particles were not instantaneous, then not all frames would have the same equations of motion and Galileo's Relativity Principle would be invalidated. This is a key assumption in classical mechanics.

We also notice that if time were somehow reversed, the Lagrangian would remain unchanged; therefore, any classical motion could be reversed.

### Deriving Newton's Equations

Using the [Euler Lagrange equation](Calculus%20of%20Variations.md#^euler-lagrange),

$$\frac{d}{dt}\Big(\frac{\partial L}{\partial \dot q}\Big) = \frac{\partial L}{\partial q}$$

we can substitute [eq. 11](#^eq-11) to get:
 
$$m_i\frac{d \textbf v_i}{dt} = -\frac{\partial U}{\partial \textbf r_i}$$

If we let $\frac{d \textbf v_i}{dt} = \textbf a_i$, and define $\textbf F = -\frac{\partial U}{\partial \textbf r_i}$, we obtain:

$$m_i a_i = F$$
^newtons-second-law

which is **Newton's second law.**


Like $U$, $\textbf F$ is also only dependent on coordinates. This might seem contradictory, but remember that this is restricted to a closed system. In a pendulum, for instance, it is evident how the force on a member is solely dependent on its position.

### Generalized-Coordinate Lagrangian

The Lagrangian for a closed system can be generalized as:

$$L = \frac12 \sum_{i,k} a_{ik}(q)\dot q_i \dot q_k - U(q) \tag{12}$$
^eq-12

Here, $\sum_{i,k}$ means we sum over every permutation of $i$ and $k$, with $n^2$ iterations. $q_i$ and $q_k$ are simply arbitrary indices, and $q$ is the set of all $q$.

### Motion in an External Field

Say a system A interacts with a system B. We can expand [eq. 11](#^eq-11) for the two systems to say that the total system of A+B (assuming it is closed) is:

$$L = L_A + L_B = T_A(q_A, \dot q_A) + T_B(q_B, \dot q_B) - U(q_A, q_B)$$

Where $T$ is the kinetic energy of each system and $U$ is the combined potential energy function. If A moves relative to B, *we can describe $q_B$ as a function of time* from A's frame. Performing this substitution gives:

$$L = T_A(q_A, \dot q_A) + T_B(q_B(t), \dot q_B(t)) - U(q_A, q_B(t))$$

Now, because $T_B$ is a function of *only time*, it could be a total time derivative of a function of time.

> I'm not going to check this myself, but I can believe that property.

As determined in [Lagrange's Equations eq. 9](Lagrange's%20Equations.md#^eq-9), the Lagrangian will remain unchanged if it varies by a total time derivative; therefore, we can neglect this term to get:

$$L = T_A(q_A, \dot q_A) - U(q_A, q_B(t)) \tag{12}$$

Now, in the presence of an external field, the potential energy function may indeed depend on time.

For a single particle, this Lagrangian would be:

$$L = \frac12 mv^2 - U(\textbf r, t) \tag{13}$$

And, by solving the Euler-Lagrange equation, the equations of motion would be:

$$m \dot{\textbf v} = - \frac{\partial U}{\partial \textbf r} \tag{14}$$

It may be the case that the force in a field is the same at all points; in this case, the field is said to be **uniform** and the potential energy can be expressed as $U = - \textbf F \cdot \textbf r$. 
*Notice the negative sign!*

> I'm not sure why the potential energy is defined as negative?