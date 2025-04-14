# Taylor Series Approximation

A first-order approximation is:

$$f(x_{i+1}) = f(x_i) + f'(x_i)(x_{i+1}-x_i)$$

This is the same as [Euler's Method](Euler's%20Method.md).

However, we can use **higher order** approximations to get a better approximation for nonlinear functions.

We do this using the Taylor series, which states:

$$f(x_{i+1}) = \sum _{n=0} ^{N} \frac{f^{(n)}(a)}{n!}(x_{i+1}-x_i)^n + R_n$$

where 
- $N$ is the number of terms in the approximation
- $R_n$ is the error

The form of $R_n$ is:

$$R_n = \frac{f^{(n+1)}(\xi)}{(n+1)!}(x_{i+1}-x_i)^{n+1}$$

We don't know what $f^{(n+1)}(\xi)$ is, but we can generally see the pattern that:

$$R_n \propto (x_{i+1}-x_i)^{n+1}$$

This allows you to see how the error changes with the order of the approximation and the size of the time step.

## Derivation

There are two ways to compute the derivative:

$$f'(x_i)=\frac{f(x_{i-1})-f(x_i)}{x_{i-1}-x_i}-O(h)$$

> $O(h)$ means that the error is proportional to $h$.

Alternatively, if we know values of $f$ in the future, we can use the **central difference** method:

$$f'(x_i)=\frac{f(x_{i+1})-f(x_{i-1})}{2h}-O(h^2)$$

> $O(h^2)$ means that the error is proportional to $h^2$.