# Calculus of Variations

**Functionals** are functions of functions:

$$D(f) \tag1$$

where $f$ is a function and $D$ is a functional. We could imagine that $D$ gives the distance along some function $f$. 

In traditional calculus, functions map from $\mathbb R$ to $\mathbb R$; now, functionals map from functions to $\mathbb R$. 

Now, imagine we are trying to minimize the distance functional $D(f)$ . We are looking for a function $f$ that will yield the lowest distance. In this example, we could express the functional as a line integral.

$$D(f) = \int \limits_{t_1}^{t_2} \;ds = \int\limits_{x_1}^{x_2} \sqrt{1+f'(x)^2}\;\; dx $$

Generally, the *primary objective of variational calculus* is to find some function $F$ such that $I[f]$ is minimized.

$$I[f] = \int\limits_{x_1}^{x_2} F(x, f(x), f'(x))\; dx \tag2$$
^eq-2

> $I$ is a functional of f

This function $F$ is called a Lagrangian. You can see how this [eq. 2](#^eq-2) is the exact same format as the [Principle of Least Action](Lagrange's%20Equations.md#^eq-1). 

### Deriving Euler-Lagrange Equation

Let's imagine that our function $f(x)$ is already optimized and satisfies [eq. 2](#^eq-2). Now, let's *transform* $f(x)$ such that it's a non-optimized function by adding some error.

$$\hat f(x) = f(x) + s \cdot \delta f (x) \tag3$$

![](../../media/excalidraw/excalidraw-2024-12-10-23.24.19.excalidraw.svg)
%%[🖋 Edit in Excalidraw](../../media/excalidraw/excalidraw-2024-12-10-23.24.19.excalidraw.md)%%

Because we want the endpoints of the two functions to remain equal, the $\delta f(x)$ term must be zero at $x_1$ (A) and $x_2$ (B). 

Let's transform the entirety of [eq. 2](#^eq-2) with the same transformation that lead to [eq. 3](#^eq-3):

$$I[\hat f] + s \delta f = \int \limits_{x_1}^{x_2} F(x, \hat f, \hat f')\; dx \tag 4$$

Then, using the **Leibniz rule** of integration, we can rewrite this as:

$$ \frac{d\ I[\hat f]}{ds} = \int \limits _{x_1}^{x_2} \partial s\cdot F(x, \hat f, \hat f')\;dx \tag 5$$
^eq-5

> Note, this video uses strange notation. $I[\hat f]$ is a constant, I believe.

If we have a function $h(x, y)$, where $x$ and $y$ are dependent to $t$, and we subject h to:

$$\partial t \cdot f(x, y)$$ We can use the chain rule to say:

$$\partial t \cdot f(x, y) = \partial x (f)\cdot \partial t (x) + \partial y (f) \cdot \partial t (y) $$

> I'm not following this, I think I might be reading the notation wrong, but I'm not too interested with the mathematical techniques used here.

We can use this chain rule property for multivariable functions on [eq. 5](#^eq-5) to get:

$$\frac{\partial I[t]}{\partial s} = \int \limits _{x_1}^{x_2}\partial s\cdot F$$








### References

```vid
https://www.youtube.com/watch?v=SQLxrr9N8zM
```
