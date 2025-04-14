# Interpolation

## Polynomial Interpolation

If you have a table of points $x$ and $y$, and you want a polynomial to go through all the points, the degree of your polynomial will be equal to the number of points you have *minus one*. In other words, $n+1$ points correspond to an $n$-degree polynomial.

For each $y_i$ and $x_i$, say:

$$y_i = a_0+a_1x_i +a_2x_i^2+\cdots +a_nx_i^n$$

Put this in a matrix and solve for $\vec a$. 

## Newton Interpolation

$$f(x)=b_0+b_1(x-x_0)+b_2(x-x_0)(x-x_1)+\cdots +b_n(x-x_0)(x-x_1)\cdots(x-x_{n-1})$$

So, when $x=x_0$, $f(x_0)=y_0=b_0$. This pattern follows for higher values. Solving for $b$ gives:

For $b_1$:

$$b_1 = \frac{f(x_1)-f(x_0)}{x_1-x_0}$$

which is effectively a finite difference.

For $b_2$:

$$b_2 = \frac{\left[\frac{f(x_2)-f(x_1)}{x_2-x_1}\right]-\left[\frac{f(x_1)-f(x_0)}{x_1-x_0}\right]}{x_2-x_0}$$

which is a finite difference of a finite difference.

Following this pattern, we get:

For $b_n$:

$$b_n = \frac{f[x_n, x_{n-1}, \cdots, x_1] - f[x_{n-1}, x_{n-2},\cdots , x_0]}{x_n-x_0}$$

Where the brackets represent a finite difference:

$$f[x_1, x_0]= \frac{f(x_1)-f(x_0)}{x_1-x_0}$$

![](excalidraw-2025-02-17-17.32.23.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2025-02-17-17.32.23.excalidraw.md)%%

Effectively, you are iteratively taking the difference for these multi-parameter calls.

## Lagrange Interpolation

Lagrange interpolation creates a set of polynomials in such a way that for each polynomial $\mathcal{L}_i(x)$, $\mathcal{L}_i(x_i)=1$ and $\mathcal{L}_i(x_j)=0$ for all $j\neq i$ (for all points that are not $x_i$). In other words, each polynomial only targets its "node," i.e., the ordered pair $(x_i, y_i)$.

Then, you multiply each Lagrange polynomial by the $y$ value at the node such that it passes through that point. If you sum all of the individual Lagrange polynomials, you get a polynomial that goes through all the points.

$$f_n(x)=\sum^n_{i=0} \mathcal{L}_i(x)f(x_i), \text{\;\;\;where\;\;\;}\mathcal L_i(x) = \prod _{j=0, j\ne i}^n\left(\frac{x-x_j}{x_i-x_j}\right)$$

If $n=1$, this expands to:

$$f_1(x)= \left(\frac{x-x_1}{x_0-x_1} \right)f(x_0)+\left( \frac{x-x_0}{x_1-x_0} \right)f(x_1)$$