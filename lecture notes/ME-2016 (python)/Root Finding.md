# Root Finding


## Open Methods

### Fixed-Point Iteration

We want to find a function that gives:

$$x_{i+1}=g(x_i)$$

For instance, if we have something like:

$$f(x)=x^2-2x+3=0$$

We can move x to one side such that we have something like:

$$x=\frac{x^2+3}{2}$$

Now, using this, you can test values of $x$; if both sides are equivalent, then that $x$ is a root.

So, to summarize:
1. Start with a random value $x$; this is your guess
2. Plug this into $g(x_i)$
3. Plug the output of $g(x_i)$ back into $g$ and keep doing this until $x_i - x_{i-1}$ is small enough

This has a **linear convergence** rate.

### Newton-Raphson

The Newton-Raphson method is very similar to Fixed-Point iteration, but instead we say:

$$x_{i+1}=x_i - \frac{f(x_i)}{f'(x_i)}$$
You can come up with this by re-arranging the Taylor series using the first two terms.

This method has a **quadratic convergence**,

$$\epsilon _{t, i+1}=\frac{f''(\xi)}{2f'(x_i)}\epsilon^2_{t,i}$$
therefore, it converges very fast in most scenarios.

However, it's possible for this method to diverge further away from the root. Also, sometimes the derivative of the function cannot be found; in these cases, we can't use the Newton-Raphson method.

### Secant Method

If we use a **backwards finite difference** to approximate the derivative of f

$$f'(x_i) \approx \frac{f(x_{i-1})-f(x)i}{x_{i-1}-x_i}$$

Then, if you substitute this into the Newton-Raphson method, we get:

$$x_{i+1} \approx x_i -\frac{f(x_i)(x_{i-1}-x_i)}{f(x_{i-1}-f(x_i))}$$

The convergence of this is **super-linear**.

Here are your updated notes with sections for **Bisection Method** and **False Position Method** in the same style.


### Modified Newton Raphson

If a function has a double root, where it doesn't change sign across the axis, we run into two issues:
1. We can't use bracketing methods because there is no sign change
2. $f'(x)=0$ at the root, so we can't use Newton-Raphson or Secant Methods

If we substitute $u(x)=f(x)/f'(x)$, then say:

$$x_{i+1}=x_i-\frac{u(x_i)}{u'(x_i)}=\frac{f(x_i)f'(x_i)}{[f'(x_i)]^2+2f(x_i)f''(x_i)}$$


## Bracketing Methods

### Bisection Method

The bisection method is a simple and reliable way to find roots, but it converges slowly. It works by repeatedly bisecting an interval [a,b][a, b] where f(a)f(a) and f(b)f(b) have opposite signs, meaning a root must exist within that interval.

1. Compute the midpoint:  
    xm=a+b2x_m = \frac{a + b}{2}
2. Evaluate f(xm)f(x_m):
    - If f(xm)=0f(x_m) = 0, then xmx_m is the root.
    - If f(xm)f(x_m) has the same sign as f(a)f(a), then set a=xma = x_m.
    - Otherwise, set b=xmb = x_m.
3. Repeat until ∣b−a∣|b - a| is smaller than a specified tolerance.

This method has a **linear convergence rate**, meaning it is slow compared to open methods, but it is guaranteed to find a root if one exists in the interval.

### False Position (Regula Falsi)

The false position method is similar to the bisection method but instead of choosing the midpoint, it approximates the root by drawing a secant line between (a,f(a))(a, f(a)) and (b,f(b))(b, f(b)), then solving for where it crosses the x-axis.

4. Compute the next approximation using:  
    $$x_i - \frac{f(x_i)(x_{i-1} - x_i)}{f(x_{i-1}) - f(x_i)}$$
5. Evaluate f(xi+1)f(x_{i+1}):
    - If $f(x_{i+1}) = 0$, then $x_{i+1}$ is the root.
    - If $f(x_{i+1})$ has the same sign as $f(a)$, set $a = x_{i+1}$.
    - Otherwise, set $b = x_{i+1}$.
6. Repeat until convergence.

Unlike the bisection method, **false position generally converges faster**, but it can fail to converge efficiently if the function is highly asymmetrical within the interval.
