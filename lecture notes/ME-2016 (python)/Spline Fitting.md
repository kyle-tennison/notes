# Spline Fitting

## Linear Splines

Straight line between every point

## Quadratic Splines

For $n+1$ points, in order to get a smooth curve, you will need $n$ intervals. Each interval is in the form of:

$$f_i(x)=a_ix^2+b_ix+c_i$$

You also know that at each internal node (i.e., the junctions between intervals, which there are $n-1$ of) the following must be true for there to be a smooth line:

$$f_{i-1}(x_{i-1})=f(x_{i-1})$$
$$f_{i}(x_{i-1})=f(x_{i-1})$$
$$f'_{i-1}(x_{i-1})=f'_i(x_{i-1})$$


