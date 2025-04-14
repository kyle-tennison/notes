# Spline Fitting

## Linear Splines

A straight line between every point.

## Quadratic Splines

For $n+1$ points, to obtain a smooth curve, you need $n$ intervals. Each interval is in the form of:

$$f_i(x)=a_ix^2+b_ix+c_i$$

You also know that at each internal node (i.e., the junction between intervals, of which there are $n-1$), the following must be true for there to be a smooth line:

$$f_{i-1}(x_{i-1})=f(x_{i-1})$$
$$f_{i}(x_{i-1})=f(x_{i-1})$$
$$f'_{i-1}(x_{i-1})=f'_i(x_{i-1})$$