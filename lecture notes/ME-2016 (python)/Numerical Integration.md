# Numerical Integration

## Trapezoidal Integration

The area under f(x) on [a, b] is:
$$(b-a)\bigg[\frac{f(a)+f(b)}{2}\bigg]$$
The error for trapezoidal integration is:

$$E_t=\int \limits _a^bR_n\,dx = \frac{-f''(\xi)}{12}(b-a)^3$$

### Multi-application Trapezoidal Integration

The error is:

$$E\propto \frac{(b-a)^3}{12n^2}\bar {f''}$$ 

where n is the number of equally spaced points.

$$I = (b-a)\bigg[ \frac{f(x_0)+2\sum_{i=1}^{n-1}f(x_i)+f(x_n)}{2n} \bigg]$$ 

The order of the error of I(h) is O(h^2).

## Richardson Extrapolation / Romberg Integration

$$I=\frac{4}{3}I(h_2)-\frac{1}{3}I(h_1)$$

where h₂ = h₁/2. In this case, the order is O(h⁴). You effectively double the accuracy of trapezoidal integration by taking the difference in this manner.

## Gauss Quadrature

By strategically choosing points on the function, you can construct a low-order polynomial that accurately represents the function.

The integral is given by:

$$I \approx c_0f(x_0)+c_1f(x_1)+\cdots+c_{n-1}f(x_{n-1})$$

If n = 2, the values will be:

$$c_0=c_1=1 \text{\;\;\;and\;\;\;}x_0 = \frac{1}{\sqrt 3}; \quad x_1=\frac{-1}{\sqrt 3}$$

You find these by asserting that:

$$
\begin{cases}
\int\limits _{a}^{b} 1\ dx =2=c_0(1)+c_1(1)\\
\int\limits _{a}^{b} x\ dx =0=c_0x_0+c_1x_1\\
\int\limits _{a}^{b} x^2\ dx =\frac{2}{3}=c_0x_0^2+c_1x_1^2\\
\int\limits _{a}^{b} x^3\ dx =0=c_0x_0^3+c_1x_1^3\
\end{cases}
$$

You do this for xⁿ, where the interval you are integrating over is [a, b]. Usually, the interval remains [0, 1] and the function is transformed so that its domain fits in this interval.