# Laplace Operator

The **Laplace Operator**[^3] $\nabla^2$ (sometimes just $\Delta$) really just means:

$$\nabla^2 f = \sum_{i=1}^n\frac{\partial ^2f}{\partial x_i^2}$$

for each cartesian coordinate $x_i$.


In 2D, this is:

$$\nabla^2f=\frac{\partial ^2 f}{\partial x^2}+\frac{\partial ^2 f}{\partial y^2}$$


Using this operator is said to be *"taking the laplacian."*

The **Vector Laplacian**[^1], i.e. the laplacian for a vector field, is:

$$\nabla^2 \textbf A= \nabla(\nabla \cdot \textbf A)-\nabla\times(\nabla \times \textbf A)$$

However, for cartesian coordinates, this is simply:

$$\nabla^2 \textbf A = (\nabla^2A_x,\nabla^2A_y, \nabla^2A_z)$$




## References

- https://en.wikipedia.org/wiki/Laplace_operator/

[^1]: https://en.wikipedia.org/wiki/Laplace_operator#Vector_Laplacian
