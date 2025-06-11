# Courant–Friedrichs–Lewy condition


The *Courant–Friedrichs–Lewy* (CFL) condition is a condition that *limits the flow distance per time step.*

![[image-31.png]]


Mathematically, the **CFL Number** is simply:

$$C_0=\frac{u \Delta t}{\Delta x}$$

Where $u$ is the velocity of flow, $\Delta t$ is the timestep, and $\Delta x$ is the cell size. The quantity $u \Delta t$ gives the *distance* that the fluid moves in one time step. If this value is greater than $\Delta x$, $C_0 > 0$; the same is true in reverse.

The **CFL Condition** limits this by saying:

$$C_0=\frac{u \Delta t}{\Delta x} \le C_{\text{max}}$$

The value of $C_{\text{max}}$ will vary depending on application. For explicit time-stepping, $C_{max}$ is typically about 1.

### References


```vid
https://www.youtube.com/watch?v=WBWY46ynRk0
Title: [CFD] The Courant (CFL) Number
Author: Fluid Mechanics 101
Thumbnail: https://i.ytimg.com/vi/WBWY46ynRk0/mqdefault.jpg
AuthorUrl: https://www.youtube.com/@fluidmechanics101
```