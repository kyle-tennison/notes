# Quantum Notes
## Position and Momentum Operators

Quantum particles, which are just extremely small things, are confined by **Heisenberg's Uncertainty Principle**: 

$$∆x∆p ≥ \frac{\hbar}{2}$$
where:
- ∆x is the uncertainty in position and
- ∆p is the uncertainty in momentum

We can never know position or momentum of a particle with supreme precision; nor can we know either measurement to infinite precision.

Because an electron falls into the particle-wave duality as well, it is simply not in the nature of the electron to exist in a infinitely precise space at a given time. The electron exists at multiple positions at any single time. 

> I wonder if other particles that are unchared, like neutrons, will also follow the Heisenberg Uncertainty Principle. They do not disturb the electric field around them, so what is stopping them from acting entirely as particles?

#### Operator Interpretation & Properties
We can also explain this with a mathematical approach. In quantum mechanics, position and momentum are mathematical operators. 

To be considered an operator, an operator $A$ must satisfy the two properties:
1) $\hat A(a\ f(x)) = a \hat A f(x)$
2) $\hat A (f(x) + g(x)) = \hat A f(x) + \hat A g(x)$
3) If $\hat S = \hat A + \hat B$, then $\hat S f = \hat A f + \hat B f$
5) If $\hat C = \beta \hat B$, then $\hat C \psi = \beta(\hat B \psi)$ 
6) If an operator $\hat A$ is observable, then $\hat A = \hat A ^{\dagger}$ , meaning the product is always real. 

Also, generally, $\hat A \hat B \ne \hat B \hat A$ . This isn't *always* the case, but it usually is.

The commutator of two operators $\hat A$ & $\hat B$ is:
$$[\hat A, \hat B] = \hat A \hat B - \hat B \hat A $$
> when acting on an function, the terms of the commutator distribute as you would expect, as if A and B are variables.


> This definition is defined in linear algebra when discussing linear operators.

#### Wave Function
To describe the uncertainty of a particle, we use the wave function $\psi$ to describe the isolated quantum system. $\psi^2$ gives a probability of the particle being at any point. More specifically, the equation is:
$$P(x)=\psi(x)^* \psi(x)=|\psi(x)|^2$$
where:
- $\psi^*$ is the "$\psi$ conjugate"
- $|\psi(x)|^2$ is the "modulus squared of psi of x"

The modulus of a complex number is $Z$ is $|Z|=\sqrt{Z \cdot Z^*}$, where $Z^*$ is the complex conjugate of the number. The complex conjugate of a complex number has an equal real part, but an opposite sign imaginary part.For instance, the complex conjugate of $a+bi$ is $a-bi$. 

When you multiply a complex number by it's conjugate, you always get a real result.

#### Operators on the Wave Function

The position operator $\hat x$ is defined as:
$$\hat x \psi(x, t) = x \psi(x, t)$$
where $x$ is the eigenvalue of $\hat x$ acting on $\psi(x)$


The momentum operator $\hat p$ is defined as:
$$\hat p \psi(x,t) = -i \hbar \frac{\partial}{\partial x} \psi(x,t)$$
where $\hbar$ is the reduced Planck constant. Note, this operator gets expanded multiple times for larger dimensions:
$$\hat p_x \psi(x,y,z,t) = -i \hbar \frac{\partial}{\partial x} \psi(x, y,z,t)$$
$$\hat p_y \psi(x,y,z,t) = -i \hbar \frac{\partial}{\partial y} \psi(x, y,z,t)$$
$$\hat p_z \psi(x,y,z,t) = -i \hbar \frac{\partial}{\partial z} \psi(x, y,z,t)$$
If you allow $\psi$ to be the wave equation $e^{i(kx-\omega t)}$, then apply the $\hat p_x$ operator, we see:
$$\hat p_x \psi = \hbar k \psi$$
This can be used to express the de Broglie relation, which is $\lambda = h/p$ . If we instead say $p = \frac{h}{\lambda}$ . 

We'll modify our operator product to expand $k$ with the wave-vector definition: $k = 2π/\lambda$, or $\lambda = 2π/k$ . Then, substitute this into the expression $p = \frac{h}{\lambda}$ to get $p = \frac{hk}{2π} = \hbar k$ .

#### Using the commutator on the wave function

If we still assume that:
$$\psi = e^{i(kx - \omega t)}$$

Using the commutator on the position and momentum operators, we get:

$$[\hat x, \hat p]\psi = \hat x \hat p \psi - \hat p \hat x \psi = x \hbar k \psi - (-i \hbar \psi +\hbar kx \psi) = i \hbar \psi  $$

So, when $\psi$ is defined like this, $[\hat x, \hat p] = i\hbar$. This relationship is the source of the heisenberg uncertainty principle.


## Wave Function Properties

A given quantum system can be described by a **set** of wave functions. These wave functions form a "Hilbert Space," which is a kind of vector space.

You can think of wave functions as vectors with potentially infinite dimensions. Each wave function is a vector in the Hilbert space, and each of them will be linearly independent; these vectors form the basis of that space; every vector is orthogonal to every other vector. So, if there are a large number of wave functions, then there are a large number of dimensions in the Hilbert space. 

#### Bra-Ket Notation

The Bra-Ket notation uses bars and kets to represent certain vectors.

- bra: $\langle \psi |$ 
- ket: $|\psi \rangle$ 

The ket is the wave function in vector form, where $\psi = a \psi_1 + b \psi_2 + \cdots$ , which is the sum of all the linearly independent wave functions that are solutions of the system.

The bra is the complex conjugate of the ket, $\psi ^*$. 

With this notation, we can define the inner product as:

$$\langle \psi_1 | \psi_2 \rangle = \int \limits_{-\infty}^{\infty}\psi_1^* \psi_2 dx $$
a few properties to note:
- The inner product of a wave function with itself is always one
- The inner product of a wave function that is not a linear combination of the first is always zero
- Sometimes, this is represented with the Kronecker delta as $\langle \psi_n | \psi_m \rangle=\delta_{n,m}$ 
- In a Hilbert space, the inner product is essentially the dot product for the wave functions

#### Normalization

When we say the probability function is normalized, we are saying:

$$\int \limits_{-\infty}^{\infty} |\psi(x)|^2dx=1$$

which basically just means there is a 100% certainty that the object exists in some region of space; in this case, $[-\infty, \infty]$. 

The Schrödinger equation happens to be linear:
$$H(t)|\psi(t)\rangle = i\hbar \frac{\partial}{\partial t}|\psi(t)\rangle$$
So, if we find a solution that does not satisfy the normalization condition—i.e., if the integral of its inner product is not equal to one—then it needs to be normalized.

Any linear combination of the solution is also a solution, meaning that we can scale a solution by a constant $a$ to normalize a solution that does not meet the normalization condition.

For instance, consider the solution $\phi_1$, which is a solution but fails to satisfy the normalization condition. We can define $\phi_2 = a\phi_1$ , such that:

$$\langle\phi_2|\phi_2\rangle = \int \limits_{-\infty}^{\infty}\phi_2^*\phi_2\ dx=\int \limits_{-\infty}^{\infty} a^*\phi_1^*a\phi_1\ dx = a^*a \int \limits_{-\infty}^{\infty}\phi_1^*\phi_1\ dx=1$$
Then, we can solve for $a$ to get a normalized wave function. It turns out that:
$$a = \frac{1}{\sqrt{\langle \phi_1|\phi_1\rangle}}$$
### Superposition Principle
For a double slit experiment, we could describe the wave function of the electron as it passes through the slit with:

$$\psi = a_L\phi_L + a_R\phi_R$$
where subscript L represents the left slit and subscript R represents the right slit. The electron has a probability of existing in either slit at a given time.