# Fracture and Failure

### Work Fracture ("Toughness")

- Area under the stress-strain curve
- Assumes the material starts uncracked

### Fracture Toughness (also "Toughness")

- Resistance of a material to crack propagation
- Most materials fail via crack propagation

Polymers tend to be brittle, like Polycarbonate and Polystyrene.

## Crack Growth

$\sigma ^*$ is the critical stress to drive **crack growth**. Applied stresses above this value *drive crack growth*. 

Cracks/notches act as stress concentrations.

$$K_{SC} = \frac{\sigma_{notch}}{\sigma_{bulk}} \approx 1+2\left(\frac{l_{notch}}{r_{notch}}\right)^{\frac12} $$

where: 
- $K_{SC}$ is the stress intensity factor
- $\sigma_{notch}$ is the stress at the notch
- $\sigma_{bulk}$ is the average (??) stress
- $l_{notch}$ is the length of the notch
- $r_{notch}$ is the radius of the curvature of the notch

For a crack, the radius would go to zero, so this equation is really just for notches.
 
## Strength/Toughness Trade-off

Around a crack, there is a *plastic zone*. The *local stress* in this zone is much higher than the *remote stress* in the rest of the part.

You can calculate the radius of the plastic zone with:

$$ r_y = \frac{\sigma_{remote} ^2 c}{\sigma ^2 _y}$$

$$K_{1c} \propto \sqrt{r_y}$$

The longer the crack, the larger the $K_{1c}$.

> 🤖 (notecheck comment) - The statement "The longer the crack, the larger the K₁c" is incorrect since K₁c is a material property and does not depend on crack length (this confusion is likely mixing K with K₁c).

## Fatigue Failure 

Fatigue failure is the result of cyclic loading/repeated stress. This *repeated loading eventually leads to micro-cracks*, which can compromise the material. These small cracks lead to stress concentrations that eventually manifest into full-blown failures.

Think about breaking the tab off of a can — you go back and forth many times until it eventually breaks off. This is an example of failure by fatigue. 

### Shot Peening

Shot peening is the process of using small spherical media to induce compressive residual stresses in a material, which can help prevent fatigue.

![|420](../../media/Pasted%20image%2020241207175746.webp)

![](../../media/Pasted%20image%2020241207175818.webp)

By adding this compression on the surface, the *material becomes more resilient to micro-cracks*, and hence, more resilient to failure by fatigue. 

### The Weibull Distribution

The Weibull distribution gives a probability for a material to fail under cyclic loading.

$$P = 1 - \exp\{-(\frac{N}{N_0})^{\beta}\} $$
where:
- $P$ is the probability of failure
- $N$ is the current number of cycles
- $N_0$ is the **characteristic lifetime** where **63%** of samples fail
- $\beta$ is the *shape parameter*, which
	- ![](../../media/Pasted%20image%2020241208152417.webp)

This distribution is used to calculate the "reliable lifetime" of a material.

## Charpy Impact Testing

```vid
https://www.youtube.com/watch?v=tpGhqQvftAo
```

Charpy impact testing uses a **pendulum to break a material sample.** The starting height of the pendulum is measured, along with the height it achieves after breaking the sample.

Some energy is absorbed in breaking the material, so the pendulum *will not return to the starting height*. You can use this information to determine the amount of energy absorbed in breaking the material.

The units you get from this test are $Pa \cdot \sqrt{m}$. I don't know why, but it is.

#### Example

You use a Charpy impact test to determine the fracture toughness of a steel specimen with a cross-sectional area of $10 cm^2$ ($0.001 m^2$). The mass of the pendulum is $10 kg$. You may assume that gravity is $10 \frac{m}{s^2}$. The pendulum is initially raised to $150 cm$, and after impacting the sample, it reaches $100 cm$. What is the fracture toughness of the material?

The change in potential energy is:

$$ \Delta PE = mg(z_2 - z_1) = (10kg)(10 \frac{m}{s^2})(1.50m - 1.00m) = 50\ J$$

Then, we can approximate the fracture toughness with:

$$K_{1c} \approx \frac{\Delta PE}{A}=50,000 {Pa}\sqrt{m}$$

> 🤖 (notecheck comment) - The expression "K₁c ≈ ∆PE / A" incorrectly yields units of J/m², not Pa√m. This is not the correct method to compute fracture toughness from Charpy data.

> This is just like wrong, but fuck this class anyways