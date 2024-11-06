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

