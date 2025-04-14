# Conservation Laws

There exist functions of $q_i$ and $\dot q_i$ that remain constant during motion and depend only on initial conditions. These values are called the **integrals of motion** and their quantity is said to be **conserved**.

As discussed in [Summing Lagrangians](Lagrange's%20Equations.md#Summing%20Lagrangians), there are $2s$ arbitrary constants that result from solving the [Euler-Lagrange equation](Calculus%20of%20Variations.md#^euler-lagrange) (where $s$ is the number of degrees of freedom). 

As discussed in [Galileo's Relativity Principle](Galileo's%20Relativity%20Principle.md), which *assumes homogeneity in space and time*, it is found that there are [no absolute quantities](Galileo's%20Relativity%20Principle.md#^no-absolutes) for time and space; in other terms, $x_0$ and $t_0$ are entirely arbitrary.

One of the arbitrary constants formed by applying the Euler-Lagrange equation is $t_0$, but as we saw, this is arbitrary. This leaves $2s-1$ other constants, which are of interest. These *constants* $C_1, C_2, \dots C_{2s-1}$ are functions of $q_i$ and $\dot q_i$ and are the *integrals of motion* for the system.

### Conservation of Energy

What follows is the derivation of the conservation of energy.

Consider an arbitrary Lagrangian $L$; if this Lagrangian exists within the constraints of [Galileo's Relativity Principle](Galileo's%20Relativity%20Principle.md), it will only depend on $q$ and $\dot q$. If we are interested in seeing the total derivative of $L$ with respect to $t$, we need to apply the [Multivariable Chain Rule](../math/multivariable%20calculus/Multivariable%20Chain%20Rule.md) to do so. 

$$\frac{dL}{dt} = \sum_i \bigg(  \frac{\partial L}{\partial q_i} \ \frac{dq_i}{dt}  + \frac{\partial L}{\partial \dot q_i}   \frac{d\dot q}{dt} \bigg ) =\sum_i \frac{\partial L}{\partial q_i}\dot q_i + \sum_i \frac{\partial L}{\partial \dot q_i} \ddot q_i$$

Then, using [Lagrange's Equations](Lagrange's%20Equations.md#^eq-7) we can substitute $\partial L /\partial q_i$ with $\frac{d}{dt}(\partial L / \partial \dot q_i)$. This allows the equation to be expressed as:

$$\frac{dL}{dt}=\sum _i \frac{d}{dt} \big(\frac{\partial L}{\partial \dot q_i} \big)\\\dot q_i+\sum_i \frac{\partial L}{\partial \dot q_i} \ddot q_i$$

We can take this one step further by applying a trick of the [Product Rule](../math/calculus/Product%20Rule.md). Notice that the first terms of each summation are $\frac{d}{dt}(\frac {\partial L}{\partial \dot q_i})$ and $\frac{\partial L}{\partial \dot q_i}$. Notice that the value in the first summation is the *time derivative* of the second. If we look at the other terms, $\dot q_i$ and $\ddot q_i$, the same is true *but in reverse*—$\ddot q_i$ is the time derivative of $\dot q_i$. 

If $f=\dot q_i$ and $g=\frac{\partial L}{\partial \dot q_i}$, the equation is stating $\sum_i g'f + gf'$, which is the product rule. So, going backwards, we could express an equivalent expression of simply $\sum_i fg$, or—reversing the substitution:

$$\frac{dL}{dt}=\sum_i\frac{d}{dt}(\dot q_i\frac{\partial L}{\partial \dot q_i}) \text{\;\;\;\;\;or, equivalently \;\;\;} 0=\frac{d}{dt}\bigg(\sum_i \dot q_i \frac{\partial L}{\partial \dot q_i} -L\bigg)$$

We now have a function of $\dot q$ that remains constant with time. If we integrate with respect to time to remove the time derivative, we get **the definition of energy:**

$$E \equiv \sum_i \dot q_i \frac{\partial L}{\partial \dot q_i} -L \tag{1}$$
^eq-1

We can express this in a more convenient way if we pull the form of the Lagrangian for a closed system; see the [Lagrangian for a System of Particles](Galileo's%20Relativity%20Principle.md#^eq-11a). The Lagrangian takes the form of $L=T(q, \dot q)-U(q)$. If we plug a Lagrangian of this form into [Eq. 1](#^eq-1), we see, first:

$$\sum_i \dot q_i \frac{\partial L}{\partial \dot q_i}=\sum_i \dot q_i \frac{\partial T}{\partial \dot q_i} = 2T$$

> The $U$ partition is independent of $\dot q$, so its contribution to the partial derivative is zero. 
> Then, as for getting $2T$ out the back, we go from $\frac{1}{2}mv^2$, then, after differentiation with respect to $v$, $mv$, then multiply by $v$ to get $mv^2$, or $2T$. 

Plugging this expression into [Eq. 1](#^eq-1), we get:

$$E=2T - (T-U)=T(q, \dot q) + U(q)$$

or, expanded for Cartesian coordinates:

$$E = \sum_i\frac{1}{2}m_iv_i^2+U(q_1, q_2, \dots)$$