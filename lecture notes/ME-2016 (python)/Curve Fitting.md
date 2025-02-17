# Curve Fitting

- **Regression** follows a pattern, *but does not pass through every point*
- **Interpolation** goes through every point

## Simple Linear Regression

The *residual* is the error between the selected line and a point. For a sample with $n$ points, you will have $n$ residuals.

Let $e_i$ be the $i^{th}$ residual of the $i^{th}$ point. If we are going to minimize the residuals, we can use the **least squares** approach, by *minimizing the following*:

$$s_r=\sum_{i=1}^ne_i^2=\sum_{i=0}^n\bigg(y_{i, meas} - (a_0+a_ix_{i, meas}) \bigg)^2 \tag{1}$$

> You can't just use any even exponent here, there's a reason why it's squared, not $2n$. 

> "meas" is short for "measured"

The values of $a_0$ and $a_1$ are the coefficients in the equation for a linear line 

$$y_{i, meas}=a_0+a_1x_{i, meas}$$

that is the regressed line.

A *necessary* condition must be satisfied for some function to meet some criterion. There are often multiple necessary conditions that must simultaneously be met. If any *sufficient* condition is satisfied, on the other hand, then the function immediately fits the criterion. 

For equation 1 to be satisfied, the following necessary conditions must be met:

$$\frac{\partial s_r}{\partial a_0} =0 \text{\;\;\;and\;\;\;} \frac{\partial s_r}{\partial a_1}=0 \tag{2}$$

Applying these conditions to Equation 1 gives the following equations:

$$0=-2\bigg(  \sum_{i=1}^n y_{i, meas} - na_0 - a_1\sum _{i=1}^nx_{i, meas}  \bigg) $$

and

$$0=-2\bigg( \sum_{i=1}^n x_{i, meas}y_{i, meas} - a_0 \sum_{i=1}^nx_{i, meas} - a_1 \sum_{i=1}^nx_{i, meas}^2 \bigg)$$

Then, you can convert both these equations into a matrix:

$$

\begin{bmatrix}

n & \sum_{i=1}^nx_{i,meas} \\
\sum_{i=1}^nx_{i,meas} & \sum_{i=1}^nx_{i,meas}^2

\end{bmatrix}

\begin{bmatrix}
a_0 \\
a_1
\end{bmatrix}

=

\begin{bmatrix}
\sum_{i=1}^ny_{i,meas} \\
\sum_{i=1}^nx_{i,meas}y_{i,meas}
\end{bmatrix}

\tag 3
$$
^eq-3

### Analyzing Error

Remember, standard deviation is given as:

$$s_y = \sqrt{\frac{\sum_{i=0}^n(y_i-\bar y)^2}{n-1}} \tag{Standard Deviation}$$

The error for a linear regression is:

$$\sqrt{\frac{s_r}{n-2}} \tag4$$

where $s_r$ is shown in Equation 1.

---

If we let 

$$s_t = \sum_{i=1}^n(y_i-\bar y)^2$$

We can say that $r^2$, a value used to measure correlation, is:

$$r^2 = \frac{s_t-s_m}{s_t}$$

## Polynomial Regression

In [[#Simple Linear Regression]], the line is modeled by:

$$y_{i, model}=a_0+a_1x_i$$

> Note that $x_i$ is the x at the experimental value,  $y_{i, model}$ is the y at the model value. In other words, the $i$ subscript represents the $i^{th}$ sample.

In polynomial regression, we can say:

$$a_0+a_1x_i+a_2x_i^2+a_3x_i^3+\cdots +a_mx_i^m$$

or, in general for a vector space, you can say:

$$y_i=a_0z_{i,0}+a_1 z_{i,1}+\cdots a_mz_{i,m}$$

or, in vector notation:

$$
\begin{bmatrix}
y_0 \\ y_1 \\ y_2 \\ \vdots \\ y_n
\end{bmatrix}

= 
\begin{bmatrix}

z_{00} & z_{01} & z_{02} & \cdots & z_{0m} \\
z_{10} & z_{11} & z_{12} & \cdots & z_{1m} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
z_{n0} & z_{n1} & z_{n2} & \cdots & z_{nm} \\

\end{bmatrix}

\begin{bmatrix}
a_0 \\ a_1 \\ a_2 \\ \vdots \\a_n
\end{bmatrix}

$$

> powers start at zero

which, when compacted, is:

$$\vec y = \textbf Z \vec a$$

The matrix $\textbf Z$ is called the **Vandermonde Matrix.**

The *error* for this model is found with:

$$S_r = \sum_{i=0}^n(y_{i, measured}-y_{i, model})^2$$

$$
S_r=\begin{cases}
(y_1-z_{10}a_0-z_{11}a_1 - \cdots - z_{1,m}a_m)^2\\
(y_1-z_{20}a_0-z_{21}a_1 - \cdots - z_{2,m}a_m)^2 \\
\vdots \\
(y_1-z_{n0}a_0-z_{n1}a_1 - \cdots - z_{n,m}a_m)^2
\end{cases}
$$


Now, when $\partial S_r / \partial a_k = 0$, the value for $a_0$ will be the value of $a_k$ that gives the smallest $S_r$.   

$$\vec 0 = \frac{\partial }{\partial a_k}(S_r)= 

\begin{cases}

2(y_1-z_{10}a_0-z_{11}a_1-\cdots - z_{1m}a_m)(-z_{1k}) \\

2(y_2-z_{20}a_0-z_{21}a_1-\cdots - z_{2m}a_m)(-z_{2k}) \\

\vdots \\
2(y_n-z_{n0}a_0-z_{n1}a_1-\cdots - z_{nm}a_m)(-z_{nk})

\end{cases}

$$

This can be expressed in a summation as:

$$0=-2 \sum_{i=0}^n\bigg[ \big (y_i - \sum_{j=0}^n  z_ja_i \big) z_{ik}  \bigg]$$

We can move this to matrix notation and say:

$$\textbf Z ^\intercal \textbf Z \;\vec a = \textbf Z^\intercal \; \vec y$$

Solving this equation for $\vec a$ will allow you to assemble the regressed polynomial. We can make this similar to [Equation 3](#^eq-3)  

## Steps for 4th Order

Given: x & y points

1. Iterate over x values
	1. Each x = one row
	2. Create 4 columns for each x, adding 1 to each power
	3. Call this the Z matrix
2. Compute $M = Z^T Z$ 
3. $b = Z^T y$ 
4. Solve $A= M^{-1}b$ 

