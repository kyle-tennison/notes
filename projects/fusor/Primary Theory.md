## Deuterium-Deuterium Fusion

Fusors that operate with the intention often use a Deuterium-Tritium reaction which can generate more energy upon fusion. However, *Tritium is extremely scarce* and there is no way for an amateur to easily obtain it. However, Deuterium is not so scarce, but it may still be difficult to source.

The underlying principle for Deuterium-Deuterium fusion is no different from other fusion; two particles are quickly accelerated at each other and collide.

### Energy to fuse

Under a mechanical lens, the energy to fuse can be derived by integrating the electrostatic force:

$$U_{coulomb} = \int \frac{1}{4π\epsilon_0}\frac{q_1 q_2}{x^2}dx = \frac{1}{4π\epsilon_0} \frac{q_1 q_2}{r} = \frac{1}{4π\epsilon_0} \frac{e^2}{r}  $$

where $e$ is the elementary charge, because $q_1$ and $q_2$ are $+1$ charged hydrogen cations.

However, evaluating the potential energy in this case would yield:

$$ U_{coulomb} = (8.99\times 10^9 \frac{Nm^2}{C^2})\frac{(1.602\times 10^{-19} C)^2}{2.128\times 10^{-15}m} \approx 677\ keV$$
where $r$ is approximately the bonding radius.
A $677keV$ barrier exists, *according to classical laws* that the particle must overcome in order to fuse. However, if this were true, we would expect to see no fusion on the sun. In reality, **quantum tunneling** plays a role in how particles can fuse

### Quantum Tunneling

Quantum tunneling is a quantum principle that, under certain conditions, particles can sometimes pass through a potential energy barrier that would otherwise be impossible to pass. This phenomena is explained by the Schrödinger equation, and it's calculation is rather involved.

The [**Gamow Factor**](https://en.wikipedia.org/wiki/Gamow_factor) greatly simplifies this calculation and explains quantum tunneling as a probability. For *any energy*, there is a probability that two particles can overcome their electrostatic barrier.

The *Gamow energy* is defined as:
$$E_G = 2m_rc^2(π\alpha Z_a Z_b)^2$$
where:
- $m_r$ is the reduced mass of the particles, i.e., $\frac{m_a m_b}{m_a+m_b}=m_r$ 
- $\alpha$ is the *fine structure constant*, also known as the "Sommerfeld Constant"
	- This is a funemental constant which quantifies the strength of electromagnetic interaction between elementary charged particles. It's relationship is described in $e^2=4π\epsilon_0 \bar h c \alpha$ , which is such an awesome equation. $\alpha = 0.00728735$ (unitless).
- $c$ is the speed of light
- $Z_a$ and $Z_b$ are the atomic numbers of each particle.

The *probability of any two particles overcoming their potential energy barrier* is given by the function:
$$P_G(E) = e^{- \sqrt{\frac{E_G}{E}}}$$
where:
- $P_G$ is the probability, $0 < P_G < 1$  (don't take these bounds as gospel)
- $E_G$ is the aforementioned Gamow energy
- $E$ is the energy (kinetic) of the particles.

Plotting this gives:
![](../../media/Pasted%20image%2020241105214223.webp)

> This is different from when I first did it, there may be an error.

From this graph, we can see that for about $50\ keV$, there is an ~16% chance of fusion to occur. Using an n-body simulation, it might be possible to estimate the number of fusion events per second with this probability, but this exceeds the scope of my project. 

## Fusor Implementation Ideation

Most amateur fusors operate around ~$60keV$, but higher voltages can exponentially help achieve more fusion, at least in this $<1\ MeV$ range—assuming the plot above is correct. 

The ionization of deuterium gas takes about $13.6\ eV$ ([source](https://en.wikipedia.org/wiki/Ionization_energy#:~:text=Hydrogen's%20ionization%20energy%20is,is%20close%20to%20the%20nucleus.)), which is negligible when compared to the overall ~$60\ keV$ required for fusion. 

We need a, say, $60 keV$ collision for the particles to have a decent chance to fuse. 

##### Kinetic Energy Ramble
This may be a silly question, but does the kinetic energy change depending on the reference frame when two particles collide?

In one scenario, the total kinetic energy here is
$$E=KE_1+\cancel{KE_2} = \frac12 m (2v)^2 = 2mv^2$$

![[../../media/excalidraw/excalidraw-2024-11-05-22.38.04.excalidraw]]

In another scenario, we can have:

$$E = KE_1+KE_2 = \frac12mv^2 +\frac12 mv^2 = mv^2$$

![[../../media/excalidraw/excalidraw-2024-11-05-22.38.50.excalidraw]]

To me, it appears that the kinetic energy is dependent on the reference frame, which should not be the case...

Ah...

The second frame is the *center-of-mass frame* where the total momentum is zero, whereas the first frame is the *lab frame*, where one particle is stationary.

In the lab frame frame, the *absolute* kinetic energy is higher, but the collision would be invariant to the frame. The conservation of energy still holds in that the total energy is still conserved in the frame (or ig not bc this is fusion but yk).

According to [wikipedia](https://en.wikipedia.org/wiki/Kinetic_energy): "The total kinetic energy of a system depends on the [inertial frame of reference](https://en.wikipedia.org/wiki/Inertial_frame_of_reference "Inertial frame of reference"): it is the sum of the total kinetic energy in a [center of momentum frame](https://en.wikipedia.org/wiki/Center_of_momentum_frame "Center of momentum frame") and the kinetic energy the total mass would have if it were concentrated in the [center of mass](https://en.wikipedia.org/wiki/Center_of_mass "Center of mass")."

The kinetic energy in the center of mass frame is given as:
$$ KE = \int \frac{v^2}2 dm = \frac12 mv^2$$
So, if we stick with the center of mass frame, there is no additional kinetic energy to account for. 

> I'm not a huge fan of this, but I'll stick with it for now and see if I get some reasonable numbers

#### Accelerating Particles

Because the net kinetic energy of the collision can be described as the sum of the two particles kinetic energies when viewed from a center-of-mass frame. 

An electron volt is defined as the energy required to accelerate an elementary charge in a $1V$ potential:
$$1 eV = 1 V \cdot e\ C=1 \cancel{V} |\frac{\frac J{\cancel C}}{\cancel{V}} | \cdot e \cancel C = 1.60\times10^{-19}J$$
Because the charge of a deuterium ion is also $+1$, or $1e$, a $1V$ potential will accelerate it to a kinetic energy of $1eV$. Hence, a $60kV$ potential will accelerate it to $60keV$ of kinetic energy. And, if the collision energy is the sum of the individual particle's kinetic energies, the collision energy will be $120keV$ if both particles collide head-on—increasing the Gamow probability of fusion to about 40% per collision.
