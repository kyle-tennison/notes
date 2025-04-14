# Parametric Equations

A **parametric equation** is an equation that depends on a parameter (often $t$), where the coordinates are functions of that variable.

For instance, in 2D Cartesian space, a function $x(t)$ and $y(t)$ will yield scalars for any value of $t$ (provided that it's within range). By sweeping across $t$, we can draw interesting curves that would not be possible with typical functions.

You can **eliminate the parameter** by solving a system of equations (given a solution exists.)

## Parametric Curves

A **cycloid** is the shape that would result by tracking a point on a circular wheel rolling through 2D Cartesian space.

$$x(t) = a(t-sin(t)), y(t) = a(1-cos(t)) \tag{Cycloid}$$

## Calculus of Parametric Curves

#### First Order Derivatives

We can define the **first order derivative**  ${dy}/{dx}$ for a parametric curve as:

$$\frac{dy}{dx}=\frac{dy/dt}{dx/dt}$$

This derivation should be self-evident. The change in $y$ is driven by $t$, and the same can be said for $x$. Then, $dt$ can cancel out because it is common between the two.

#### Second Order Derivatives

If we want the **second order derivative**, i.e. $\frac{d^2y}{dx^2}$, we would simply say:

$$\frac{d^2y}{dx^2}= \frac{d}{dx}\left(\frac{dy}{dx}\right)$$

Alternatively, we could also say:

$$\frac{d^2x}{dy^2}= \frac{d}{dy}\left(\frac{dy}{dx}\right)$$
> 🤖 (notecheck comment) - The expression for the second derivative of x with respect to y is incorrect. The correct expression should involve d/dy(dx/dy), not d/dy(dy/dx).

#### Integrals of Parametric Curves

The integral of a parametric curve can be derived as follows:

If we are interested in the area under the curve, the differential area would be no different from a non-parametric one:

$$dA = y(t) \cdot dx$$

We can introduce a $dt$ term into this equation that cancels out:

$$dA = y(t) \cdot \frac{dx}{dt}dt$$
Then, integrating both sides yields:

$$A = \int _a^b y(t) \cdot \frac{dx}{dt}dt = \int_a^b y(t)x'(t)\ dt $$

You could follow a similar procedure the other way around to integrate using $x(t)$ and $y'(t)$. 

#### Arc Length

The differential arc length can be defined as the following using simple geometry:

$$dS = \sqrt{dx^2 + dy^2}$$

We can add $dt$ to this differential with the following:

$$dS = \frac{1}{dt} \sqrt{dx^2+dy^2}\ dt = \sqrt{\frac{dx^2+dy^2}{dt^2}}\ dt = \sqrt{\frac{dx^2}{dt^2}+ \frac{dy^2}{dt^2}}\ dt = \sqrt{x'^2+y'^2}\ dt $$

Then, all we have to do is integrate:

$$S = \int \limits _{t_0}^{t_1} \sqrt{x'^2 + y'^2} dt $$