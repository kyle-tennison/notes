# Control Volume Work

The equation 

$$ W = \int \limits _1^2 p dV $$

is *only applicable to control volumes* (why 😭😭). 

If we want an expression for work across a one-inlet, one-exit control volume, we can use the T ds relationships to drive one.

Remember:

$$ dU = \delta Q - \delta W \Rightarrow dU = T dS - pdV$$

> Why can we use the differential of work here and not the full integral? 
> ^ This equation isn't used directly, it's substituted into the control volume balance.

This gives the first $T\ ds$ relationship:


$$ T\ dS = dU + p dV $$

We can convert this into the second $T \ ds$ relationship by adding enthalpy. Remember:

$$ H = U + pV, \Rightarrow dH = dU + d(pV) = dU + pdV + Vdp$$
$$dU + pdV = dH-Vdp$$ 
Which can get substituted into the first $T\ ds$ relationship to get:

$$ T dS = dH - Vdp \tag{6}$$

Normalizing this relationship by mass, then integrating both sides, gives the relationship:

$$ \int \limits_1^2 T ds = (h_2- h_1) - \int \limits_1^2 v dp$$

or, rearranged for simplicity:

$$ \int \limits_1^2 T ds + (h_1-h_2) =  - \int \limits_1^2 v dp \tag{7}$$

 If we step back for a second and look at the energy balance for a *steady state, reversible* control volume, which is (if rearranged)...

$$ \frac{\dot W_{cv}}{\dot m} = \frac{\dot Q_{cv}}{\dot m} + (h_1 -h_2) + (\frac{V_1^2-V_2^2}{2})+g(z_1-z_2) \tag{8}$$

... we can replace the heat and enthalpy terms with Eq. 7 to get:

$$ \frac{\dot W_{cv}}{\dot m} = - \int \limits _1^2 vdp + (\frac{V_1^2+V_2^2}{2})+g(z_1-z_2) \tag{9}$$

And, finally, *if kinetic and potential energy is neglected*, the equation reduces to:

$$ \frac{\dot W_{cv}}{\dot m} = - \int \limits _1^2 vdp \tag{10}$$

Visualized, this is:

![](../../media/Pasted%20image%2020241108202145.webp)



## Alternate Derivation




When working in a **closed system** the *boundary work* is expressed by:

$$W=  \int \limits_1^2 p \ dV \tag{Closed System}$$

However, **flow work** in a control volume in an **adiabatic environment**, where *KE and PE are neglected* is:

$$ \dot W_{cv} = \dot m(h_1-h_2) \Rightarrow \frac{\dot W_{cv}}{\dot m} = (h_1-h_2)  $$

That change in enthalpy, which represents the flow work, can be expressed as:

$$ (h_1-h_2) = -\int _1^2 v\ dp$$

If the process is reversible and adiabatic and reversible, meaning:

$$ \frac{\dot W_{cv}}{\dot m} = - \int \limits _1^2 v\ dp \tag{Control Volume}$$

