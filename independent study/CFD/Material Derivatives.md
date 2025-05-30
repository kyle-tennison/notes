# Material Derivatives

Material derivatives are a continuum mechanics concept that describes the *rate of change* of some physical quantity of a **[Material Element](https://en.wikipedia.org/wiki/Fluid_parcel)** (i.e., an infinitesimal volume—also called a **Fluid Parcel**) that is within a velocity field that depends on space and time.

Other names for the material derivative include:

- advective derivative
- convective derivative
- derivative following the motion
- hydrodynamic derivative
- Lagrangian derivative
- particle derivative
- substantial derivative
- substantive derivative
- Stokes derivative
- total derivative

For a macroscopic tensor field $y(\textbf{x}, t)$, the Material Derivative is defined as:

$$\frac{Dy}{Dt} \equiv \frac{\partial y}{\partial t} + \textbf{u}\cdot \nabla y$$

where $\nabla y$ is the *[covariant derivative](https://en.wikipedia.org/wiki/Covariant_derivative)* of the tensor and $\textbf{u}(\textbf{x}, t)$ is the flow velocity. The $\textbf{u}\cdot \nabla y$ term can be thought of as the directional derivative in the $\textbf{u}$ direction: $(\textbf{u}\cdot \nabla)y$.

Really, conceptually, all the Material Derivative is doing is *combining local changes with global changes.* ChatGPT gave me a good example:

---

Imagine you're floating down a river in a kayak. The **temperature of the water** varies from place to place and also changes over time. If you want to know how **the temperature feels to you as you drift**—that is the **material derivative** of temperature. It accounts for:

1. **Local change over time** (how the temperature changes at a fixed point).
    
2. **Change due to motion** (how moving into warmer or cooler areas changes what you feel).