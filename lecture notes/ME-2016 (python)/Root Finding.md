# Root Finding

## Open Methods

### Fixed-Point Iteration

We want to find a function that gives:

$$x_{i+1}=g(x_i)$$

For instance, if we have something like:

$$f(x)=x^2-2x+3=0$$

we can rearrange the equation to isolate x such that we have:

$$x=\frac{x^2+3}{2}$$

Now, using this formulation, you can test values of $x$; if both sides are equal, then that $x$ is a root.

So, to summarize:
1. Start with an initial guess for $x$.
2. Plug this into $g(x_i)$.
3. Plug the output of $g(x_i)$ back into $g$ and continue this process until $x_i - x_{i-1}$ is sufficiently small.

This method has a **linear convergence** rate.

### Newton-Raphson

The Newton-Raphson method is very similar to fixed-point iteration, but instead we define:

$$x_{i+1}=x_i - \frac{f(x_i)}{f'(x_i)}$$

This can be derived by rearranging the Taylor series using its first two terms.

This method has a **quadratic convergence**,

$$\epsilon_{t, i+1}=\frac{f''(\xi)}{2f'(x_i)}\epsilon^2_{t,i}$$

Therefore, it converges very fast in most scenarios.

However, it is possible for this method to diverge away from the root. Also, sometimes the derivative of the function is not available; in these cases, we cannot use the Newton-Raphson method.

### Secant Method

If we approximate the derivative of f using a **backwards finite difference**:

$$f'(x_i) \approx \frac{f(x_{i-1})-f(x_i)}{x_{i-1}-x_i}$$

then, substituting this into the Newton-Raphson method yields:

$$x_{i+1} \approx x_i -\frac{f(x_i)(x_{i-1}-x_i)}{f(x_{i-1})-f(x_i)}$$

The convergence of this method is **super-linear**.

### Modified Newton Raphson

If a function has a double root where it does not change sign across the axis, we encounter two issues:
1. We cannot use bracketing methods because there is no sign change.
2. $f'(x)=0$ at the root, so we cannot use the Newton-Raphson or Secant methods.

If we substitute $u(x)=f(x)/f'(x)$, then:

$$x_{i+1}=x_i-\frac{u(x_i)}{u'(x_i)}=\frac{f(x_i)f'(x_i)}{[f'(x_i)]^2+f(x_i)f''(x_i)}$$

> 🤖 (notecheck comment) - The final formula for the modified Newton-Raphson iteration is missing the xᵢ term and has an incorrect sign in the denominator. A correct version is x₍ᵢ+1₎ = xᵢ - [f(xᵢ) f′(xᵢ)] / [f′(xᵢ)² − f(xᵢ) f″(xᵢ)].

## Bracketing Methods

### Bisection Method

The bisection method is a simple and reliable way to find roots, but it converges slowly. It works by repeatedly bisecting an interval [a, b] where f(a) and f(b) have opposite signs, so a root exists within that interval.

1. Compute the midpoint:  
   $$x_m = \frac{a + b}{2}$$
2. Evaluate $f(x_m)$:
   - If $f(x_m) = 0$, then $x_m$ is the root.
   - If $f(x_m)$ has the same sign as $f(a)$, then set $a = x_m$.
   - Otherwise, set $b = x_m$.
3. Repeat until $|b - a|$ is smaller than a specified tolerance.

This method has a **linear convergence rate**, meaning it is slower compared to open methods, but it is guaranteed to find a root if one exists in the interval.

### False Position (Regula Falsi)

The false position method is similar to the bisection method, but instead of choosing the midpoint, it approximates the root by drawing a secant line between (a, f(a)) and (b, f(b)), then solving for where it crosses the x-axis.

4. Compute the next approximation using:  
   $$x_i - \frac{f(x_i)(x_{i-1} - x_i)}{f(x_{i-1})-f(x_i)}$$
5. Evaluate $f(x_{i+1})$:
   - If $f(x_{i+1}) = 0, then $x_{i+1}$ is the root.
   - If $f(x_{i+1})$ has the same sign as $f(a)$, set $a = x_{i+1}$.
   - Otherwise, set $b = x_{i+1}$.
6. Repeat until convergence.

Unlike the bisection method, **false position generally converges faster**, although it can fail to converge efficiently if the function is highly asymmetrical within the interval.