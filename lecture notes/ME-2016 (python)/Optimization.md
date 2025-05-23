# Optimization

We are trying to find a value $x$ that makes some function $f(x)$ a minimum value. $x$ may be an $n$-dimensional vector.

We let the value $x^*$ minimize the function; i.e., $f(x^*)$ is the minimum of $f$. 

## Unconstrained Optimization

### Analytical Approach

For *1-dimensional* unconstrained optimization (i.e. $n=1$), we can say:

If $x^*$ is a *local* minimum, then it will be true that:

1. $f'(x^*)=0\to\text{first-order necessary condition}$
2. $f''(x^*)>0\to \text{second-order necessary condition}$

If $f$ is modified by a constant $c$, the value $x^*$ that minimizes $f$ will also minimize $cf$. 

## Gradient Descent

Covered in my other note: [2. Gradient Descent](2.%20Gradient%20Descent.md)

The *first order* condition that $f'(x^*)=0$ can be expressed as:

$$\nabla f(x) = \begin{bmatrix}
\frac{\partial f}{\partial x_1} \\
\frac{\partial f}{\partial x_2} \\
\vdots \\
\frac{\partial f}{\partial x_n} \\
\end{bmatrix} = \vec{0}
$$

The *second order* condition that $f''(x^*)=0$ can be expressed as:

> 🤖 (notecheck comment) - The second order condition for a local minimum should require that $f''(x^*)>0$ in 1D or, in multidimensional settings, that the Hessian is positive definite (all eigenvalues > 0) rather than being equal to 0.

$$
\nabla^2 f(x) =
\begin{bmatrix}
\frac{\partial^2 f}{\partial x_1^2} & \frac{\partial^2 f}{\partial x_1 \partial x_2} & \cdots & \frac{\partial^2 f}{\partial x_1 \partial x_n} \\
\frac{\partial^2 f}{\partial x_2 \partial x_1} & \frac{\partial^2 f}{\partial x_2^2} & \cdots & \frac{\partial^2 f}{\partial x_2 \partial x_n} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial^2 f}{\partial x_n \partial x_1} & \frac{\partial^2 f}{\partial x_n \partial x_2} & \cdots & \frac{\partial^2 f}{\partial x_n^2}
\end{bmatrix}
$$

This matrix is called the **Hessian**; all its eigenvalues are positive at a local minimum.

### Descent Method

The general idea behind descent is that we start at an initial guess $x_0$, then iteratively move toward a minimum by moving in the opposite direction of the gradient, which will always be the direction of steepest descent.

$$x_{i+1}=x_i-\nabla f(x_i)h$$

In vector form, this is:

$$
\begin{bmatrix}x_1\\x_2\\ \vdots \\x_n \end{bmatrix}_{i+1} = \begin{bmatrix}x_1\\x_2\\ \vdots \\x_n\end{bmatrix}_i- \begin{bmatrix} \frac{\partial f}{\partial x_1} \\\frac{\partial f}{\partial x_2} \\ \vdots \\ \frac{\partial f}{\partial x_n} \end{bmatrix}_i h
$$

For a *one-dimensional* problem, this simplifies to:

$$x_{i+1}=x_i-f'(x_i)h$$

which can easily be implemented with any of the methods previously discussed.

### Optimal Step Size

If we were to find some function $g(h)$ that was minimized at the value of $h^*$ that yielded the quickest descent, we could speed up our method of descent.

1. Obtain some function $g(h)$, and solve $\text{min}_h\, g(h)$ to get $h^*$.
2. Proceed in finding $x_{i+1} = x_i - \nabla f(x_i) h^*$ 

To find $g(h)$, start with:

$$f(x_{i+1}) = f(x_{1, i+1}, x_{2, i+1}, \dots) = f \left( x_{1,i} + \left( \frac{\partial f}{\partial x_1} \right)_i h, x_{2,i} +\left( \frac{\partial f}{\partial x_2} \right)_i h, \dots \right)$$

> 🤖 (notecheck comment) - In gradient descent the update is defined as $x_{i+1}=x_i-\nabla f(x_i)h$, so the arguments inside $f$ should be $x_{i}+ \big[-h \left(\frac{\partial f}{\partial x}\right)_i\big]$, meaning the gradient terms should be subtracted rather than added.

On the RHS of this equation, there are three variables: $x$, $\nabla f(x_i)$, and $h$. We can express this as:

$$= f(\underbrace{x_i, \nabla f(x_i)}_{\text{constants}}, h)$$

However, notice that $x_i$ and $\nabla f(x_i)$ are known constants at $i$. Hence, this reduces to a single-variable function of $h$. We can then treat $f$ as $g$, and solve $\text{min}_h\, g(h)$ to solve for $h^*$. 

## Constrained Optimization

The general form is:

$$
\begin{aligned}
&\min_{x} f(x) \\
&\text{such that} \\
&d_i(x) \leq a_i,\quad i = 1, 2, \ldots, m \\
&e_i(x) = b_i,\quad i = 1, 2, \ldots, p \\
&x_i^{\min} \leq x_i \leq x_i^{\max},\quad i = 1, 2, \ldots, n
\end{aligned}
$$

We want to find $x$ such that $f(x)$ reaches a minimum while following the constraints that $d_i(x) \leq a_i$, $e_i(x)=b_i$, and each $x_i \in [x_i^{\text{min}}, x_i^{\text{max}}]$.

We say that:
- $d = \{d_1, d_2, \dots, d_m\}$ are the *inequality constraint functions*
- $e = \{e_1, e_2, \dots, e_p\}$ are the *equality constraint functions*
- $a_i$, $b_i$, $x_i^{\text{min}}$, $x_i^{\text{max}}$ are all constants

To solve a constrained optimization problem like this, use `scipy.optimize.minimize()` with the `method="SLSQP"`.