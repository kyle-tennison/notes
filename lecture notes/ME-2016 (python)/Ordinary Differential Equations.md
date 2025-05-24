# Ordinary Differential Equations

An $n^{th}$ order ODE requires $n$ conditions to arrive at a unique solution.

## IVP ODEs

Recap: an ODE has one independent variable. An $n^{th}$-order ODE's highest derivative is order $n$. An $n^{th}$ order ODE requires $n$ auxiliary conditions for a unique solution. An IVP gives all aux. conditions at the same independent value; whereas a BVP gives aux. conditions at arbitrary values.

### Taylor Series Approach (IVP)

The Taylor series (Eq. \ref{eq:taylor-series}) expansion about the initial conditions can be used to *iteratively* approximate $y(x_{i+1})$:

$$

y(x_{i+1}) = y(x_i) + y'(x_i)(x_{i+1} - x_i) + \cdots

$$

*Note*: Often, the notation that $f(x_i, y_i) = y'(x_i)$ is used.

An $n^{th}$-order Taylor series will be perfect for an $n^{th}$-order Taylor series. The *truncation error* is of order $O((x_{i+1} - x_i)^{n+1})$.

However, while $f(x_i, y_i)$ is often known, higher order derivatives may not be known and another method is needed.

### Euler's Method

Euler's method is simply a first-order Taylor series application:

$$

y_{i+1} - y_i + f(x_i, y_i) h.

$$

The *local* truncation error is $O(h^2)$ and the *global* truncation error is $O(h)$.

### Heun's Method

This method first predicts the future value of $y$ using the Euler method, i.e.

$$

y^0_{i+1} = y_i + f(x_i, y_i) h.

$$

Then, we compute the slope at this new location with $y'_{i+1} = f(x_{i+1}, y_{i+1}^0)$. Then, we *correct* the earlier prediction using the average of the initial slope and the future slope:

$$

y_{i+1} = y_i + \frac{f(x_i, y_i) + f(x_{i+1}, y_{i+1}^0)}{2} h

$$

This yields an error of order $O(h^2)$.

![[image-30.png]]

### Midpoint Method

This is also a **predictor-corrector** method, like Heun's method, except we add another point at $x_{i+1/2}$ (the midpoint) to predict. The prediction

$$

y_{i+1/2}^0 = y_i + f(x_i, y_i) \frac{h}{2}

$$

is made, then the derivative is taken

$$

y'_{i+1/2} = f(x_{i+1/2}, y_{i+1/2}^0).

$$

Then, this estimate is corrected:

$$

y_{i+1} \approx y_i + f(x_{i+1/2}, y_{i+1/2}^0) h.

$$

The order of error here is $O(h^2)$.

### Runge-Kutta Method

The general form of the Runge-Kutta method (which is for IVPs) is:

$$

y_{i+1} = y_i + \underbrace{\phi(x_i, y_i, h)}_{\text{increment function}} h

$$

where the *increment function* is a slope estimate in the form of:

$$

\phi = a_1 k_1 + a_2 k_2 + \dots + a_n k_n

$$

where:

$$

\begin{aligned}

&k_1 = f(x_i, y_i) \\

&k_2 = f(x_i + p_1 h, y_i + q_{11} k_1 h) \\

&k_3 = f(x_i + p_2 h, y_i + q_{21} k_1 h + q_{22} k_2 h) \\

&\vdots \\

&k_n = f\left(x_i + p_{n-1} h, y_i + q_{n-1,1} k_1 h + q_{n-1,2} k_2 h + \cdots + q_{n-1,n-1} k_{n-1} h\right)

\end{aligned}

$$

You can solve for $a$'s, $q$'s, and $p$'s by setting this equation equal to the terms in the Taylor series (Eq. \ref{eq:taylor-series}).

#### First-Order

Runge-Kutta method has $\phi = a_1 k_1$. From the Taylor series, you can say $k_1 = f(x_i, y_i)$ and $a_1 = 1$.

#### Second-Order

In the second-order, the increment function is:

$$

\phi = f\left(x_i + \underbrace{\frac{1}{2}}_{p_1} h, y_i + \underbrace{\frac{1}{2}}_{q_{11}} \underbrace{f(x_i, y_i)}_{k_1} h \right)

$$

#### Third-Order

$$

\begin{aligned}

y_{i+1} &= y_i + \frac{1}{6} (k_1 + 4 k_2 + k_3) h \\

k_1 &= f(x_i, y_i) \\

k_2 &= f\left(x_i + \frac{1}{2} h, y_i + \frac{1}{2} k_1 h \right) \\

k_3 &= f(x_i + h, y_i - k_1 h + 2 k_2 h)

\end{aligned}

$$

The error is $O(h^3)$.

#### Fourth-Order

$$

\begin{aligned}

y_{i+1} &= y_i + \frac{1}{6} (k_1 + 2 k_2 + 2 k_3 + k_4) h \\

k_1 &= f(x_i, y_i) \\

k_2 &= f\left(x_i + \frac{1}{2} h, y_i + \frac{1}{2} k_1 h \right) \\

k_3 &= f\left(x_i + \frac{1}{2} h, y_i + \frac{1}{2} k_2 h \right) \\

k_4 &= f(x_i + h, y_i + k_3 h)

\end{aligned}

$$

The error is $O(h^4)$.

## BVP ODEs

### Shooting Method

^9586fd

The idea is that, if you reduce a BVP to an IVP, you can solve it with an existing method. This requires the BVP to have a unique solution.

For example, if we are going from

$$

\frac{d^2 y}{dx^2} = f(x, y, y'); \quad y(x_0) = y_0; \quad y(x_1) = y_1

$$

to

$$

\frac{d^2 y}{dx^2} = f(x, y, y'); \quad y(x_0) = y_0; \quad y'(x_0) = a,

$$

we need to find the value $a$ such that

$$

y(x_1, a) - y_1 = 0.

$$

This becomes a root finding problem.

If there is a second-order ODE, you may need to break it into two first-order ODEs, those being:

$$

\begin{aligned}

&\frac{dy}{dx} = z; \quad y(x_0) = y_0 \\

&\frac{dz}{dx} = f(x, y, z); \quad z(x_0) = a

\end{aligned}

$$

So, in summary:

1. Find some function that you want to find the root of; $g(a) = y(x_1, a) - y_1 = 0$. Use previous methods to solve the IVP to obtain this $y(x)$.

2. Specify an initial guess for the root finding method.

3. Perform the root finding.

4. Use $a$ to solve the IVP and BVP.

### Finite Difference Method

Assume the domain $[0, L]$ is discretized into $N+1$ equally spaced nodes. Define a node by

$$

x_i = i\, \Delta x, \quad \Delta x = \frac{L}{N}, \quad i=0, 1, \ldots, N.

$$

The boundary conditions are applied at $x_0$ and $x_N$.

For a BVP such as

$$

\frac{d^2 T}{dx^2} = k (T - T_a), \quad T(0) = T_l, \quad T(L) = T_r,

$$

the second derivative at an interior node $x_i$ (with $i=1, \dots, N-1$) is approximated by

$$

\frac{d^2 T}{dx^2} \Big|_{x=x_i} \approx