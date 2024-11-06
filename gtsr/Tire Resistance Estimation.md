
## Problem

We need to know how much power is lost at nominal velocity due to tire friction with the ground. Modeling this value can allow us to evaluate whether a component is advantageous to the overall efficiency of the car, or if it's mass outweighs its benefit.

As the tires are compressed, they deform more and in turn dissipate more energy to heat. Therefore, a relationship resists between the weight on the tires and the dissipated energy.
$$\dot Q_f(V, m)$$
Where
- $\dot Q_f$ is the power lost to friction from heat
- $V$ is velocity
- $m$ mass of the vehicle
We assume that the temperature of the tire and its pressure are constant over the duration of the trip.

### Estimations

Based solely on intuition, I expect the result to show that, roughly, $\dot Q_f \propto V$ and that $\dot Q_f \propto m^k$ where $k>1$, meaning that the power loss is exponential to mass. Again, these values are solely inferences based off of no actual experimental results.

## Theory

A tire generates heat in two primary ways:
1) Hysteretic heat generation
2) Surface heat generation

##### Hysteretic heat generation

This heat generation is due to the elastic nature of a viscoelastic material, where some heat is loss due to the strain of the material. 

##### Surface Heat generation

Surface heat generation is caused by slip with the road. With large slip angles, this becomes significant; however, this effect is likely negligible 

![|307](../media/Pasted%20image%2020241105184245.png)

#### Estimating Rolling Friction
Wikipedia Article