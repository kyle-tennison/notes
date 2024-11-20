# Fracture

### Work Fracture ("Toughness")

- Area under the stress-strain curve
- Assumes the material starts un-cracked

### Fracture Toughness (also "Toughness")

- Resistance of a material to crack propagation
- Most materials fail via crack propagation

Polymers tend to be brittle, like Polycarbonate and Polystyrene.

## Crack Growth

$\sigma ^*$ is the critical stresses to drive **crack growth**. Applied stresses above this value *drive crack growth*. 

Cracks/notches act as stress concentrations.

$$K_{SC} = \frac{\sigma_{notch}}{\sigma_{bulk}} \approx 1+2(\frac{l_{notch}}{r_{notch}})^{(\frac12)} $$

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

