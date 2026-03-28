# R5b. Fracture Mechanics

## Linear Elastic Fracture Mechanics

Aka LEFM. 

If the zone of yielding around the crack is small, then LEFM is a good analysis tool; it assumes that the bulk of the material is within the linear-elastic domain. 

### Modes of Crack Displacement

![](excalidraw-2026-02-22-18.14.41.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-02-22-18.14.41.excalidraw.md)%%

Each of these will require a different technique, but the first one, Mode I, is the most common. 

For mode (1), specifically in a **semi-infinite plane**, similar to [here](R4b.%20Stresses%20&%20Concentrations.md#Semi-Infinite%20Plate), the stress around the crack tip, expressed in polar coordinates, is:

$$
\left.
\begin{aligned}
\sigma_x  &= \frac{K}{\sqrt{2\pi r}} \cos\left(\frac{\theta}{2} \right) \left[1- \sin \left(\frac \theta 2\right)\sin \left(\frac {3\theta} 2\right) \  \right] + \dots\\\\
\sigma_y  &= \frac{K}{\sqrt{2\pi r}} \cos\left(\frac{\theta}{2} \right) \left[1+ \sin \left(\frac \theta 2\right)\sin \left(\frac {3\theta} 2\right) \  \right] + \dots\\\\
\tau_{xy}  &= \frac{K}{\sqrt{2\pi r}} \sin \left(\frac \theta 2\right)\cos \left(\frac \theta 2\right)\cos \left(\frac {3\theta} 2\right) \  + \dots\\\\
\sigma_z &= \nu (\sigma_x + \sigma_y)\\\\
\tau_{yz}&=\tau_{xz} = 0
\end{aligned}
\quad \right\}\quad \text{(Mode I)}
$$

> I have no clue where these come from or what the higher order values would be.

If you take the von Mises of the stresses above and plot them against $\theta$ and $r$, we can get an idea of how the stress is distributed:


![](excalidraw-2026-02-22-18.27.11.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-02-22-18.27.11.excalidraw.md)%%


The value $K$ in the equations above, sometimes shown as $K_I$ for Mode I, is called the **stress intensity factor**. When dealing with a plate where the crack roughly in the center and $b \gg a$ , the stress intensity factor is:

$$K = \sigma_{\rm norm} \sqrt{\pi a}, \qquad \text{when } b \gg a $$

where $a$ is the half-width of the crack and $\sigma_{\text {norm}}$ is the normal stress (calculated without subtracting the crack area from the cross section). 

> Just to be clear on this one: you *do* update the cross-section area for [Stress Concentrations](R4b.%20Stresses%20&%20Concentrations.md), but *do not* for cracks.

If $b \cancel{\gg} a$ , or the crack is non-center, this equation gets adjusted to be:

$$K = \beta \sigma_\text{norm} \sqrt{\pi a}$$

where $\beta$ is a dimensionless quantity that depends on the geometry. For *cracks on the edge of a plate* with $b \gg a$, $\beta = 1.12$:

$$K = 1.12 \sigma_{\text{norm}}\sqrt{\pi a},\qquad \text{(Edge Crack)}$$

## Fracture Toughness

A crack is considered to be in a **stable mode** as long as:

$$K < K_c$$

where $K_c$ is the **fracture toughness** (a material property). When $K > K_c$, the crack will propagate suddenly to catastrophic failure. The corresponding factor of safety is:

$$N_\text{FM} = \frac{K_c}{K}$$

where the $\text{FM}$ is for Fracture Mechanics.



