## Fundamental Principle
The mass of an atom is not just the mass of its protons and neutrons.

Helium-4, which has 2 protons and 2 neutrons, has an atomic mass of 4.00153u. However, the mass of two protons and two neutrons on their own—i.e., when they are not combined into an atom—is 4.04188u. When these particles bond to create an atom, a small amount of mass is converted into energy.

^ This amount of energy is called the **Binding Energy ∆**, which is the energy released in fusion.

The binding energy for each atom is different:
![[Pasted image 20241018195352.png]]

Eventually, these get so heavy that they release energy when broken apart, not when joined. This is fission. However, the energy released by fusion is much greater (~4x) than that released by fission per unit mass.

## How it's done
Commonly, two hydrogen isotopes—deuterium (1 neutron) and tritium (2 neutrons)—are combined to make helium-4 (with an extra spare neutron). 

$$^2_1H + ^3_1H \rightarrow _2^4He+^1_0n$$

In this equation, **mass is not conserved**; the energy released is given as $E_0 = mc^2$.

## Current issues
Tritium is extremely rare, and tokamaks need a lot of it.
Currently, tokamaks use a lithium blanket to regenerate tritium. The extra proton from fusion splits the lithium into helium and tritium. However, this is very inefficient (~20%).

> 🤖 (notecheck comment) - It is the neutron from the fusion reaction that interacts with lithium to produce helium and tritium, not an extra proton.

Alternatively, you could use beryllium, but it's extremely expensive and also radioactive because it has uranium impurities. This means that their blankets will become radioactive with time, meaning that they will face the same issues as fission reactors.

Helion Energy uses deuterium and helium-3 as fuel. Helium-3 is extremely rare; however, you can (ironically) fuse two deuterium atoms to create it. 

Tokamak reactors use the released neutron to generate heat, which is converted into electricity using a steam turbine. However, Helion relies on magnetic fields for energy generation. They use the analogy that, after compressing the gas with magnetic fields, it pushes back after fusion, just like a piston compressing a combusting gas. However, this approach cannot harness energy from neutrons; hence, they need charged particles to push back.

# Safety Considerations

To realistically achieve fusion at a hobbyist level, a deuterium–deuterium reaction is necessary due to the scarcity of tritium and helium-3.

$$^2H+^2H \rightarrow\ ^3He + ^1n$$

## Neutron Radiation

If fusion is achieved, neutron radiation will become an issue. Neutron radiation is a form of ionizing radiation. These "free neutrons" react with the nuclei of other atoms to create new nuclides, which may correspond to potentially dangerous isotopes. Additionally, free neutrons are unstable and decay into a proton, an electron, and an electron antineutrino.

From a health perspective, one of the more severe concerns is neutron activation, which is the ability of a free neutron to induce radioactivity in an otherwise stable source. In other words, it can render you radioactive (not cool!).

This means that I need to consider how the metals used could potentially become radioactive. For instance, stainless steel can form cobalt-60 when hit with a neutron and become radioactive; the half-life of this is 5.27 years.

Another mitigation can simply be short runtimes. Less overall neutron radiation corresponds to less hazard.

A water medium can be used to "moderate" neutron exit. The $^1H^+$ in water interacts with the neutrons, slowing them down until they are sufficiently low in energy.

There are probably some government regulations regarding neutron production, so I'll keep these in mind.

## What you see online
Many people online claiming to make "fusors" are really just ionizing the surrounding air (even though it is mostly in a vacuum). The purple seen is identical to that in a high voltage nitrogen tube: 

## X-Ray Radiation

X-rays are produced in X-ray tubes by accelerating an electron in an electron field, then rapidly decelerating it by crashing it into the "target."

This type of radiation is called "Bremsstrahlung radiation," from German "Bremsen" meaning "to break" and "Strahlung" meaning radiation. The rapid loss in kinetic energy of the particle is converted into a high-energy photon, which will tend to be an X-ray.

For a fusor operation in the 15-30kV range, electrons colliding with the anode or any other material in the fusor can create X-rays.