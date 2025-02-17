# Interpolation


## Polynomial Interpolation

If you have a table of points $x$ and $y$, and you want a polynomial to go through all the points. The degree of your polynomial will be equal to the number of points you have *minus one*. In other words $n+1$ points corresponds to an $n$ degree polynomial.


For each $y_i$ and $x_i$, say:

$$y_i = a_0+a_1x_i +a_2x_i^2+\cdots +a_nx_i^n$$

Put this in a matrix and solve for $\vec a$. 

## Newton Interpolation

$$f(x)=b_0+b_1(x-x_0)+b_2(x-x_0)(x-x_1)+\cdots +b_n(x-x_0)(x-x_1)\cdots(x-x_{n-1})$$

So, when $f(x_0)$, $y_0=b_0$. This pattern follows for higher values. Solving for $b$ gives:

For $b_1$:

$$b_1 = \frac{f(x_1)-f(x_0)}{x_1-x_0}$$

which is effectively a finite-difference.

For $b_2$:

$$b_2 = \frac{[\frac{f(x_2)-f(x_1)}{x_2-x_1}]-[\frac{f(x_1)-f(x_0)}{x_1-x_0}]}{x_2-x_0}$$

which is a finite-difference of a finite difference.

Following this pattern, we get:

For $b_n$:

$$b_n = \frac{f[x_n, x_{n-1}, \cdots, x_1] -f[x_{n-1}, x_{n-2},\cdots , x_0]}{x_n-x_0}$$

Where the brackets represent a finite difference:

$$f[x_1, x_0]= \frac{f(x_1)-f(x_0)}{x_1-x_0}$$

![](excalidraw-2025-02-17-17.32.23.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2025-02-17-17.32.23.excalidraw.md)%%

Effectively, you are iteratively taking the difference for these multi-parameter calls.

---

