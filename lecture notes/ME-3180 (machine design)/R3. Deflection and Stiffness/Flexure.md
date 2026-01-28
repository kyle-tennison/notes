# Flexure

In the [Derivation](Bending%20Stress.md#Derivation) of bending stress, we defined $\rho$ to be the radius of curvature of bending. This differs from curvature $\kappa$ with the relationship:

$$\text{curvature} = \kappa = \frac 1 \rho$$

According to the book, curvature can also be calculated with the following:

$$\kappa = \frac{d^2y/dx^2}{\left[1+(dy/dx)^2\right]^{3/2}}$$
where the denominator $\to 1$, so

$$\kappa \approx \frac{d^2y}{dx^2}$$

> Not totally sure how this works. Rusty on this.

If we substitute this into the [bending equation](Bending%20Stress.md#^radius-of-curvature-bending-eq) $\displaystyle {\frac{1}{\rho}} = \frac{M}{EI}$, we get:

$$\frac{M}{EI} = \frac{d^2y}{dx^2}$$

This is also [shown here](8.%20Bending.md#^curvature-equation) in COE-3001.

Subsequent differentiations give:

$$\frac{V}{EI} = \frac{d^3y}{dx^3}$$

$$\frac{q}{EI} = \frac{d^4y}{dx^4}$$

Also, from we can use small angle approximation to say that the angle of deformation is:
$$dy=dx\,\sin(\theta) \approx \theta \,dx\qquad\Rightarrow\qquad \theta \approx \frac{dy}{dx}$$
---

Each higher order differentiation requires an additional boundary layer. You will often need to fix $\theta$ and/or $y$ at the endpoints.

