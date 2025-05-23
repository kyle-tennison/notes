# Conservation Laws

There exist functions of $q_i$ and $\dot q_i$ that remain constant during motion and depend only on initial conditions. These values are called the **integrals of motion** and their quantity is said to be **conserved**.

As discussed in [Summing Lagrangians](Lagrange's%20Equations.md#Summing%20Lagrangians), there are $2s$ arbitrary constants that result from solving the [Euler-Lagrange equation](Calculus%20of%20Variations.md#^euler-lagrange) (where $s$ is the number of degrees of freedom). 

As discussed in [Galileo's Relativity Principle](Galileo's%20Relativity%20Principle.md), which *assumes homogeneity in space and time*, it is found that there are [no absolute quantities](Galileo's%20Relativity%20Principle.md#^no-absolutes) for time and space; in other words, $x_0$ and $t_0$ are entirely arbitrary.

One of the arbitrary constants formed by applying the Euler-Lagrange equation is $t_0$, but as we saw, this is arbitrary. This leaves $2s-1$ other constants, which are of interest. These *constants* $C_1, C_2, \dots, C_{2s-1}$ are functions of $q_i$ and $\dot q_i$ and are the *integrals of motion* for the system.

### Conservation of Energy

What follows is the derivation of the conservation of energy.

Consider an arbitrary Lagrangian $L$; if this Lagrangian exists within the constraints of [Galileo's Relativity Principle](Galileo's%20Relativity%20Principle.md), it will only depend on $q$ and $\dot q$. If we are interested in finding the total derivative of $L$ with respect to $t$, we need to apply the [Multivariable Chain Rule](../math/multivariable%20calculus/Multivariable%20Chain%20Rule.md) to do so. 

$$\frac{dL}{dt} = \sum_i \bigg(  \frac{\partial L}{\partial q_i} \ \frac{dq_i}{dt}  + \frac{\partial L}{\partial \dot q_i}   \frac{d\dot q}{dt} \bigg ) =\sum_i \frac{\partial L}{\partial q_i}\dot q_i + \sum_i \frac{\partial L}{\partial \dot q_i} \ddot q_i$$

Then, using [Lagrange's Equations](Lagrange's%20Equations.md#^eq-7) we can substitute $\partial L /\partial q_i$ with $\frac{d}{dt}(\partial L / \partial \dot q_i)$. This allows the equation to be expressed as:

$$\frac{dL}{dt}=\sum _i \frac{d}{dt} \big(\frac{\partial L}{\partial \dot q_i} \big)\\\dot q_i+\sum_i \frac{\partial L}{\partial \dot q_i} \ddot q_i$$

We can take this one step further by applying a trick of the [Product Rule](../math/calculus/Product%20Rule.md). Notice that the first terms of each summation are $\frac{d}{dt}(\frac{\partial L}{\partial \dot q_i})$ and $\frac{\partial L}{\partial \dot q_i}$. The value in the first summation is the *time derivative* of the second. Similarly, $\ddot q_i$ is the time derivative of $\dot q_i$. 

If $f=\dot q_i$ and $g=\frac{\partial L}{\partial \dot q_i}$, the equation is stating $\sum_i g'f + gf'$, which is the product rule. So, going backwards, we could express an equivalent expression as simply $\sum_i fg$, or—reversing the substitution:

$$\frac{dL}{dt}=\sum_i\frac{d}{dt}(\dot q_i\frac{\partial L}{\partial \dot q_i}) \text{\;\;\;\;\;or, equivalently \;\;\;} 0=\frac{d}{dt}\bigg(\sum_i \dot q_i \frac{\partial L}{\partial \dot q_i} -L\bigg)$$

We now have a function of $\dot q$ that remains constant with time. If we integrate with respect to time to remove the time derivative, we get **the definition of energy:**

$$E \equiv \sum_i \dot q_i \frac{\partial L}{\partial \dot q_i} -L \tag{1}$$
^eq-1

We can express this in a more convenient way if we use the form of the Lagrangian for a closed system; see the [Lagrangian for a System of Particles](Galileo's%20Relativity%20Principle.md#^eq-11a). The Lagrangian takes the form of $L=T(q, \dot q)-U(q)$. If we plug a Lagrangian of this form into [Eq. 1](#^eq-1), we see, first:

$$\sum_i \dot q_i \frac{\partial L}{\partial \dot q_i}=\sum_i \dot q_i \frac{\partial T}{\partial \dot q_i} = 2T$$

> The $U$ partition is independent of $\dot q$, so its contribution to the partial derivative is zero. Then, to obtain $2T$, we start from $\frac{1}{2}mv^2$, differentiate with respect to $v$ to get $mv$, and then multiply by $v$ to get $mv^2$, or $2T$. 

Plugging this expression into [Eq. 1](#^eq-1), we get:

$$E=2T - (T-U)=T(q, \dot q) + U(q)$$

or, expanded for Cartesian coordinates:

$$E = \sum_i\frac{1}{2}m_iv_i^2+U(q_1, q_2, \dots)$$



## Momentum

If $L$ is varied by an infinitesimal change in position $\epsilon$, we can say:

$$\delta L = \sum_i \frac{\partial L}{\partial q_i}\cdot \delta q=\epsilon\cdot \sum_i \frac{\partial L}{\partial q_i}$$

Because *space is homogeneous*, the Lagrangian should not change with position, meaning this shift of $\epsilon$ will result in $\delta L =0$.

$$\delta L = \epsilon \cdot \sum_i \frac{\partial L}{\partial q_i}=0$$

Because $\epsilon$ is nonzero, the $\sum_i \frac{\partial L}{\partial q_i}$ factor must be zero; hence, we can state that:

$$\sum_i \frac{\partial L}{\partial q_i}=0$$

Now, if we look at the [Euler-Lagrange equation](app://obsidian.md/Calculus%20of%20Variations.md#^euler-lagrange), in the form of:

$$\frac{d}{dt}(\frac{\partial L}{\partial \dot q})=\frac{\partial L}{\partial q}$$
We can cancel the right-hand side to obtain:

$$\frac{d}{dt}(\frac{\partial L}{\partial \dot q})=\cancel{\frac{\partial L}{\partial q}}=0$$

From this, we can see that the quantity $\partial L / \partial \dot q$ remains fixed with respect to time—i.e. it's quantity is conserved. This quantity is **momentum**, defined as:

$$P \equiv \sum _i \frac{\partial L}{\partial \dot q_i}$$
^momentum

If $L=\frac{1}{2}mv^2$, we can see that:

$$P=\sum_im_iv_i$$


In a potential energy field, only some components of momentum will be conserved. For example, the x & y components of momentum will be conserved in a frame with z-component gravity.

Next, because we said $\sum_i \frac{\partial L}{\partial q_i}=0$, if $L=\sum_i \frac{1}{2}mv_i^2+U(q)$ , we are saying:

$$\sum_i \frac{\partial U}{\partial q_i}=\sum_iF_i=0$$

That is, in a closed system, the sum of *applied forces* on all the particles is zero. 

Using the aforementioned property, that the sum of forces in a closed system is zero: *if two particles in a closed system are to exert a force on each other, the force exerted by the first particle on the second particle is **equal in magnitude, and opposite in direction**, to that exerted by the second particle on the first.* This is the origin of **Newton's third law**.


When using generalized coordinates, $p_i=\partial L/\partial \dot q_i$ are called the *generalized momenta* and $F_i=\partial L / \partial q_i$ are called the *generalized forces*. This allows us to express Lagrange's equations in a new form:

$$\underbrace{\dot p_i=F_i}_{\text{Euler-Lagrange Equations}}$$


### Problem

![[image-23.png]]

![](excalidraw-2025-05-17-22.49.27.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2025-05-17-22.49.27.excalidraw.md)%%

In this system, $T=\frac{1}{2}mv^2$ and $U$ is either $U_1$ or $U_2$, depending on its location. Hence, the energy balance is:

$$\frac{1}{2}mv_1^2+U_1=\frac{1}{2}mv_2^2+U_2$$

> Note, $E=T+U$ but $L=T-U$

We can also assert the conservation of momentum, but we can only do this in the direction that's perpendicular to the potential energy function. This gives:

$$mv_1sin(\theta_1)=mv_2sin(\theta_2)$$

We can rearrange this to get:

$$\frac{sin(\theta_1)}{sin(\theta_2)}=\frac{\cancel{m}v_2}{\cancel{m}v_1}$$

If we solve the energy balance for $v_2$, we get:

$$v_2=\sqrt{\frac{mv_1^2+2(U_1-U_2)}{m}}$$

substituting this gives:

$$\frac{sin(\theta_1)}{sin(\theta_2)}=\frac{1}{v_1}\sqrt{\frac{mv_1^2+2(U_1-U_2)}{m}}=\underbrace{\sqrt{1+\frac{2(U_1-U_2)}{v_1^2m}}}_{\text{solution}}$$


## Center of Mass

The momentum of a system will change depending on the frame's velocity relative to the motion. There will always be a frame that can satisfy:

$$\sum_im_iv_i=0$$
You can relate the momentum of two frames with:

$$P=P'+V\sum_im_i$$

where V is the difference in velocity between the two frames. If, in the equation above $P'$ is the frame with no momentum, it's quantity will be zero and the equation reduces to:

$$P=V\sum_im_i \qquad \text{or} \qquad V=P/\sum_im_i = \frac{\sum_im_i\textbf{v}_i}{\sum_im_i}$$

This velocity $V$ is the velocity of the frame relative to the frame with zero momentum. Also, notice that $V$ is the total time derivative of $R$, as defined below:

$$R \equiv \frac{\sum_i m_i\textbf{r}_i}{\sum_i m_i}$$

This quantity $R$ is the *center of mass*, and it allows us to think of a collection of particles similar to how we think of a single particle. We can ten extend the law of inertia for a system of particles: the center of mass will move in a straight line at constant velocity in a closed system. 

The velocity $V$ is also used to express the total energy of a system:

$$E=\frac{1}{2}\mu V^2+E_i$$

where $\mu = \sum_i m_i$ and $E_i$ represents the internal energy (i.e., motion between particles). This is a helpful simplification when considering many particles. 

If $E'$ is the energy in a system relative to some other system $E$, where $E=\frac{1}{2}\sum m_iv_i^2 +U$, then:

$$\begin{align*}
E' &= \frac{1}{2} \sum_i m_i v'_i + U \\
   &= \frac{1}{2} \sum_i m_i (v_i + V)^2 + U \\
   &= \underbrace{\frac{1}{2} \sum_i m_i v_i^2 + U}_{E}
   + V \cdot \underbrace{\sum_i m_i v_i}_{P}
   + \frac{1}{2} \underbrace{\sum_i m_i}_{\mu} V\\
   &=E+V\cdot P+\frac{1}{2}\mu V^2
\end{align*}
$$


You can also transfer between Lagrangians with:

$$L'=L+V\cdot P+\frac{1}{2}\mu V^2$$

and action with:

$$S'=S+\mu V\cdot R+\frac{1}{2}\mu V^2t$$

