# Quantum Notes
## Position and Momentum Operators

Quantum particles, which are extremely small things, are confined by **Heisenberg's Uncertainty Principle**:

$$∆x∆p ≥ \frac{\hbar}{2}$$
where:
- ∆x is the uncertainty in position, and
- ∆p is the uncertainty in momentum.

We can never know the position or momentum of a particle with absolute precision; nor can we measure either quantity with infinite precision.

Because electrons exhibit particle-wave duality, it is simply not in their nature to exist in an infinitely precise space at a given time. An electron exists at multiple positions at any single time.

> I wonder if other particles that are uncharged, like neutrons, will also follow the Heisenberg Uncertainty Principle. They do not disturb the electric field around them, so what is stopping them from acting entirely as particles?

#### Operator Interpretation & Properties
We can also explain this with a mathematical approach. In quantum mechanics, position and momentum are represented by mathematical operators.

To be considered an operator, an operator $A$ must satisfy the following properties:
1) $\hat A(a\ f(x)) = a \hat A f(x)$  
2) $\hat A (f(x) + g(x)) = \hat A f(x) + \hat A g(x)$  
3) If $\hat S = \hat A + \hat B$, then $\hat S f = \hat A f + \hat B f$  
5) If $\hat C = \beta \hat B$, then $\hat C \psi = \beta(\hat B \psi)$  
6) If an operator $\hat A$ is observable, then $\hat A = \hat A^{\dagger}$, meaning the product is always real.

Also, generally, $\hat A \hat B \ne \hat B \hat A$. This isn't *always* the case, but it usually is.

The commutator of two operators $\hat A$ and $\hat B$ is:
$$[\hat A, \hat B] = \hat A \hat B - \hat B \hat A $$
> When acting on a function, the terms of the commutator distribute as you would expect, as if A and B were variables.

> This definition is given in linear algebra when discussing linear operators.

#### Wave Function
To describe the uncertainty of a particle, we use the wave function $\psi$ to represent the isolated quantum system. $\psi^2$ gives the probability of the particle being at any point. More specifically, the equation is:
$$P(x)=\psi(x)^* \psi(x)=|\psi(x)|^2$$
where:
- $\psi^*$ is the "$\psi$ conjugate,"
- $|\psi(x)|^2$ is the "modulus squared of $\psi$ at $x$."

The modulus of a complex number $Z$ is $|Z|=\sqrt{Z \cdot Z^*}$, where $Z^*$ is the complex conjugate of the number. The complex conjugate of a complex number has an equal real part but an opposite-signed imaginary part. For instance, the complex conjugate of $a+bi$ is $a-bi$.

When you multiply a complex number by its conjugate, you always get a real result.

#### Operators on the Wave Function

The position operator $\hat x$ is defined as:
$$\hat x \psi(x, t) = x \psi(x, t)$$
where $x$ is the eigenvalue of $\hat x$ acting on $\psi(x)$.

The momentum operator $\hat p$ is defined as:
$$\hat p \psi(x,t) = -i \hbar \frac{\partial}{\partial x} \psi(x,t)$$
where $\hbar$ is the reduced Planck constant. Note that this operator is expanded for larger dimensions:
$$\hat p_x \psi(x,y,z,t) = -i \hbar \frac{\partial}{\partial x} \psi(x, y, z, t)$$
$$\hat p_y \psi(x,y,z,t) = -i \hbar \frac{\partial}{\partial y} \psi(x, y, z, t)$$
$$\hat p_z \psi(x,y,z,t) = -i \hbar \frac{\partial}{\partial z} \psi(x, y, z, t)$$
If you allow $\psi$ to be the wave function $e^{i(kx-\omega t)}$, then applying the $\hat p_x$ operator, we see:
$$\hat p_x \psi = \hbar k \psi$$
This can be used to express the de Broglie relation, which is $\lambda = h/p$. Alternatively, we can write $p = \frac{h}{\lambda}$.

We'll modify our operator product to expand $k$ with the wave-vector definition: $k = 2π/\lambda$, or $\lambda = 2π/k$. Then, substituting into the expression $p = \frac{h}{\lambda}$, we get $p = \frac{hk}{2π} = \hbar k$.

#### Using the Commutator on the Wave Function

If we still assume that:
$$\psi = e^{i(kx - \omega t)}$$

Using the commutator on the position and momentum operators, we get:

$$[\hat x, \hat p]\psi = \hat x \hat p \psi - \hat p \hat x \psi = x \hbar k \psi - (-i \hbar \psi + \hbar k x \psi) = i \hbar \psi$$

So, when $\psi$ is defined like this, $[\hat x, \hat p] = i\hbar$. This relationship is the source of the Heisenberg uncertainty principle.

## Wave Function Properties

A given quantum system can be described by a **set** of wave functions. These wave functions form a "Hilbert Space," which is a kind of vector space.

You can think of wave functions as vectors with potentially infinite dimensions. Each wave function is a vector in the Hilbert space, and each of them will be linearly independent; these vectors form the basis of that space, and every vector is orthogonal to every other vector.
> 🤖 (notecheck comment) - In a Hilbert space, vectors (wave functions) are not automatically orthogonal to every other vector. Only when an orthonormal basis is chosen do the basis vectors satisfy mutual orthogonality. In general, a set of normalized vectors need not be orthogonal unless explicitly constructed to be so.

#### Bra-Ket Notation

The Bra-Ket notation uses bras and kets to represent certain vectors.

- bra: $\langle \psi |$
- ket: $|\psi \rangle$

The ket represents the wave function in vector form, where $\psi = a \psi_1 + b \psi_2 + \cdots$, which is the sum of all the linearly independent wave functions that are solutions of the system.

The bra is the complex conjugate of the ket, $\psi^*$.

With this notation, we can define the inner product as:

$$\langle \psi_1 | \psi_2 \rangle = \int \limits_{-\infty}^{\infty}\psi_1^* \psi_2\,dx$$
A few properties to note:
- The inner product of a wave function with itself is always one.
> 🤖 (notecheck comment) - The inner product of a wave function with itself equals one only if the wave function is normalized. In general, ⟨ψ|ψ⟩ can differ from one and normalization is required to set it to one.
- The inner product of a wave function that is not a linear combination of the first is always zero.
> 🤖 (notecheck comment) - Zero inner product between two wave functions is a property of orthogonal functions. In a general Hilbert space, two distinct wave functions are not automatically orthogonal unless they belong to an orthonormal set.
- Sometimes, this is represented with the Kronecker delta as $\langle \psi_n | \psi_m \rangle=\delta_{n,m}$.
- In a Hilbert space, the inner product is essentially the dot product for the wave functions.

#### Normalization

When we say the probability function is normalized, we mean:

$$\int \limits_{-\infty}^{\infty} |\psi(x)|^2\,dx=1$$

which basically means there is a 100% certainty that the object exists in some region of space; in this case, $[-\infty, \infty]$.

The Schrödinger equation happens to be linear:
$$H(t)|\psi(t)\rangle = i\hbar \frac{\partial}{\partial t}|\psi(t)\rangle$$
So, if we find a solution that does not satisfy the normalization condition—i.e., if the integral of its inner product is not equal to one—then it needs to be normalized.

Any linear combination of solutions is also a solution, meaning that we can scale a solution by a constant $a$ to normalize a solution that does not meet the normalization condition.

For instance, consider the solution $\phi_1$, which is a solution but fails to satisfy the normalization condition. We can define $\phi_2 = a\phi_1$, such that:

$$\langle \phi_2|\phi_2\rangle = \int \limits_{-\infty}^{\infty}\phi_2^*\phi_2\,dx=\int \limits_{-\infty}^{\infty} a^*\phi_1^*a\phi_1\,dx = |a|^2 \int \limits_{-\infty}^{\infty}\phi_1^*\phi_1\,dx=1$$
Then, we can solve for $a$ to get a normalized wave function. It turns out that:
$$a = \frac{1}{\sqrt{\langle \phi_1|\phi_1\rangle}}$$

### Superposition Principle
For a double slit experiment, we could describe the wave function of the electron as it passes through the slits with:

$$\psi = a_L\phi_L + a_R\phi_R$$
where the subscript L represents the left slit and the subscript R represents the right slit. The electron has a probability of existing in either slit at a given time.