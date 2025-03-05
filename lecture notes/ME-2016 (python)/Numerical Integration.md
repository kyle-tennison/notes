# Numerical Integration


## Trapezoidal Integration

The area of $f(x) \in [a,b]$ is:
$$(b-a)\bigg[\frac{f(a)+f(b)}{2}\bigg]$$
The error for trapezoidal integration is:

$$E_t=\int \limits _a^bR_nd x = \frac{-f''(\xi)}{12}(b-a)^3$$

### Multi-application Trapezoidal Integration

The error is:

$$E\propto \frac{(b-a)^3}{12n^2}\bar {f''}$$ where $n$ is the number of spaced points.

$$I = (b-a)\bigg[ \frac{f(x_0)+2\sum_{i=1}^{n-1}f(x_i)+f(x_n)}{2n} \bigg]$$ 