Chapter 9, [Lecture Notes](Refrigeration%20Cycles%20(Lecture).md)

---


### Vapor Refrigeration Systems

**Refrigeration systems** are exactly what they sound like they are; these are things like refrigerators, air conditioners, and liquid nitrogen generators.

**Heat pumps** are similar to refrigeration cycles, but their goal is to pump heat from a cold reservoir.

Both heat pumps and refrigeration systems require input work.


#### Carnot Refrigeration Cycle

A Carnot refrigeration cycle is a Carnot cycle that runs in reverse. Just like any other Carnot cycle, it operates between two reservoirs at $T_H$ and $T_C$ and its T-s diagram makes a perfect rectangle.

$$\beta_{max} = \frac{T_C}{T_H-T_C}$$ ![](../../media/excalidraw/excalidraw-2024-11-08-18.20.01.excalidraw.svg)
%%[🖋 Edit in Excalidraw](../../media/excalidraw/excalidraw-2024-11-08-18.20.01.excalidraw.md)%%


In this cycle, the cold temperature is typically below the surrounding temperature.

In the real world, there are many reasons a Carnot cycle is not feasible.
1. Running a compressor with a liquid-vapor mixture is complex; it's much easier to compress a vapor.
2. Putting a turbine in one of these systems is often unrealistic; instead, it's often switched for a #throttling-valve , which is a type of valve that maintains constant enthalpy between input and output.
3. Stray heat transfer causes irreversibilities, causing the cycle to stray from the perfectly rectangular Carnot cycle.

An actual cycle would look more like:

![|347](../../media/excalidraw/excalidraw-2024-11-08-18.20.02.excalidraw.svg)
%%[🖋 Edit in Excalidraw](../../media/excalidraw/excalidraw-2024-11-08-18.20.02.excalidraw.md)%%

### Analyzing Ideal Vapor-Compression Refrigeration Systems

An ideal vapor-compression cycle will have the following T-s diagram:

![](../../media/Pasted%20image%2020241108182931.webp)

#### Heat In

$\dot Q_{in}$ is called the **refrigeration capacity**. If KE, PE are neglected, *and it is assumed that pressure is constant across the evaporator,* we can find the heat in from the evaporator as:
$$ \frac{\dot Q_{in}}{\dot m} = h_1 - h_4 $$
> This makes sense because pressure is constant and temperature increasing. Perfect time to use enthalpy.

#### Compressor Work

Using a steady-state control volume analysis where $\dot Q_{cv}$ is neglected, along with kinetic and potential energy, we can show that work into the compressor is:

$$\frac{\dot W_{c}}{\dot m} = h_2 - h_1$$

> I think this abandons the sign convention that work in is negative. Just be ready for that.

#### Rejected Heat

Just like we did for heat in over the evaporator, the heat out over the compressor can be derived with:
$$ \frac{\dot Q_{out}}{\dot m} = h_2 - h_3 $$
> Again, I'm pretty sure this abandons the sign convention where heat out is usually negative.

#### Expansion Valve

The primary characteristic of a #throttling-valve (which I assume is analogous to an expansion valve??) is that the *enthalpy across it* is constant. In this case, this means

$$h_4 = h_3 $$

Note that, **across an ideal expansion valve, entropy is not constant.** If entropy were constant across the expansion valve, it would be impossible for the state to change—hence, there is some unavoidable heat transfer across the valve. **Throttling processes are inherently irreversible.**

#### Coefficient of performance

The coefficient of performance of a refrigeration cycle is

$$ \beta = \frac{\dot Q_{in}/\dot m}{\dot W_c / \dot m}= \frac{h_1-h_4}{h_2-h_1}$$
### Analyzing real vapor-compression systems

In real vapor compression systems, we must consider the #isentropic-efficency of the compressor:

$$ \eta_c = \frac{(\dot W_c / \dot m)_s}{(\dot W_c /\dot m)} = \frac{h_{2s}-h_1}{h_2-h_1} $$
Additionally, *superheated vapor exists the evaporator* (state 1) (as compared to the saturated vapor in the ideal system) and *subcooled liquid exits the condenser* (as compared to the saturated liquid in the ideal system).


