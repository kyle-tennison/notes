# Divergence Theorem

*The following is written by AI and modified by Kyle Tennison*

The Divergence Theorem (also known as Gauss's Theorem) relates the flux of a vector field $\mathbf{F}$ across a closed surface $\mathbf{S}$ to the volume integral of the divergence of $\mathbf{F}$ over the volume $\mathbf{V}$ enclosed by $\mathbf{S}$:

$$
\iint_{S} \mathbf{F} \cdot d\mathbf{S} = \iiint_{V} (\nabla \cdot \mathbf{F}) \, dV
$$

## Derivation

Let **F** be a continuously differentiable vector field defined on a closed, bounded volume **V** with a piecewise smooth boundary surface **S**, oriented outward.

1. **Start with the definition of divergence:**

   $$
   \nabla \cdot \mathbf{F} = \lim_{V \to 0} \frac{1}{V} \oint_{\partial V} \mathbf{F} \cdot \mathbf{n} \, dS
   $$

   This describes the average flux density exiting an infinitesimal volume.

2. **Apply the integral form over a finite volume:**

   Divide **V** into infinitesimal volume elements \( \delta V_i \). The total flux through **S** is the sum of the fluxes through the boundary of each \( \delta V_i \). Internal surface contributions cancel out due to opposite orientations, so only the boundary surfaces contribute:

   $$
   \sum \iint_{\partial (\delta V_i)} \mathbf{F} \cdot \mathbf{n} \, dS \to \iint_{S} \mathbf{F} \cdot d\mathbf{S}
   $$

3. **Transition to the volume integral:**

   By summing over all $\delta V_i $ and taking the limit as $\delta V_i \to 0$:

   $$
   \iiint_{V} (\nabla \cdot \mathbf{F}) \, dV = \iint_{S} \mathbf{F} \cdot d\mathbf{S}
   $$

   Thus, the theorem is proven.

### Sources
- M. R. Spiegel, *Vector Analysis*, Schaum’s Outline Series.
- D. J. Griffiths, *Introduction to Electrodynamics*, 4th Ed., Pearson.
- Arfken & Weber, *Mathematical Methods for Physicists*.