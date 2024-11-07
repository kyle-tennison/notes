11/5/24

---

Effectively a power cycle run in reverse

![](../../media/Pasted%20image%2020241105140408.png)

This is exactly what air conditioners do; they move heat from a hot reservoir to a cooler reservoir using work.

**Capacity** is the rate of heat transfer, which could be $Q_h$ or $Q_c$. 
- If you are dealing with a "Refrigeration" cycle, it refers to $Q_c$
- If you are dealing with a "Heat Pump," it refers to $Q_H$

The $ton$ unit is the power needed to melt $1\ ton$ of ice in 24 hours. $1 ton \approx 3.5kW$ .

**Coefficients of Performance**
The coefficient depends on which cycle is being analyzed because there are different goals.

$\beta = \frac{Q_C}W$ (Refrigerator)
$\gamma = \frac{Q_H}W$ (Heat Pump)

These efficiencies have their own Carnot efficiencies.

## Carnot Refrigeration Cycle

![](../../media/Pasted%20image%2020241105141336.png)
> **condenser and evaporator are flipped in this drawing**

Because this is a Carnot cycle, everything is idealized. Meaning,
- 1 --> 2 — Isentropic Compression
- 2 --> 3 — Isothermal cooling
- 3 --> 4 — Isentropic expansion
- 4 --> 1 — Isothermal heating

Also note:
- Pressure across the condenser and evaporator are constant

The T-s diagram would be: 
![](../../media/Pasted%20image%2020241105141609.png)

In this case, the coefficients of performance would be at their maximum (while adhering to the 2nd law).

$$\beta = 1-\frac{T_C}{T_H}, \ \ \gamma = 1+\beta$$
> These are the maximum allowed coefficients of performance for any cycle efficiency; exceeding this will violate the second law.

In reality, you can't really pull this Carnot cycle *off* 
- It's hard to send a 2-phase liquid through a compressor
- Fitting a turbine into an air conditioner or anything small is impractical.

## Vapor Compression Refrigeration Cycle

![](../../media/Pasted%20image%2020241105142355.png)

> Again, **condenser and evaporator are flipped in this drawing**

The only difference in this cycle is the turbine is replaced with an expansion valve, which is effectively a throttle. 

**Expansion valves** are a special type of valve that has *constant enthalpy* across it. The common model is to *neglect heat and work.* Note that $S_{in} \ne S_{out}$, $T_{in} \ne T_{out}$, and $P_{in} \ne P_{out}$ . 

The T-s diagram for a vapor compression cycle:
![](../../media/Pasted%20image%2020241105142939.png)


Most of the time, the working fluid will be *Refrigerant-134a*, but there are some other popular ones too.

#### Example: Ideal Vapor Compression Refrigeration Cycle

**KNOWN**: 
$\dot m = 0.08 \frac{kg}s$ 
$T_{evap}=273K$  
$T_{cond}=299K$ (this corresponds to $T_3$, even though the temp into the condenser)

**FIND**: 
a) Equation for $\dot W_{comp}$
b) $\dot Q_{in}$

**ENGINEERING MODEL:**
- All components are ideal

**ANALYSIS:**

1) Find entropy at state 1, which is a sat vapor, using temp
2) Find $h_{2s}$ using $s_{2s}={s_1}$, and knowing that $p_3=p_2=p_{sat}$ 
3) $\dot W_{comp} = \dot m (h_{2s}-h_1)$ , derived from control volume balence
4) Find $h_3=h_{sat}=h_4$ 
5) $\dot Q_{in} = \dot m (h_1-h_4)$ 


#### Non-Ideal Vapor Compression Cycle

Creating an effective heat exchanger is often difficult; this can be the source of many inefficiencies. 

You need to start considering $h_2$ instead of $h_{2s}$ . 

$$\dot Q_c = \dot m (h_1-h_4)$$ 

### Brayton Refrigeration Cycles

Brayton cycles can also be run in reverse to work as a refrigeration cycle:

![](../../media/Pasted%20image%2020241107140939.png)

In one of these cycles, the working fluid is still air. To solve a problem like this, you are usually given the *pressure ratio.*

The pressure ratio is defined as $\frac{p_2}{p_1}$ .

To solve a problem like this, you will need to find the enthalpy at each state.

---
#### Example Analysis

##### Finding Enthalpies

The enthalpy at $1$ can be found if $T_1$ is known from the ideal gas tables for Air.

If the pressure ratio is known, you can assert:

$$\frac{p_2}{p_1} = \frac{p_{2r}}{p_{1r}}$$ 
If the enthalpy is known for the ideal gas, $p_{1r}$ can also be found, meaning that: 

$$p_{2r} = \frac{p_2}{p_1}p_{1r}$$
If we solve for $p_{2r}$, we can interpolate on the ideal gas tables find the corresponding temperature, enthalpy, and entropy at state $2$.

A similar process can be applied to find $h_3$ and $h_4$. In a Brayton cycle, it is assumed that $p_2 = p_3$ and $p_4 = p_1$ ; therefore, 

$$\frac{p_2}{p_1} =\frac{p_3}{p_4} = \frac{p_{3r}}{p_{4r}}$$

After finding $p_{3r}$ for $T_3$, you can solve the equation above for $p_{4r}$ and interpolate to find $h_4$ and $T_4$. 


##### Energy Balence

![[../../media/excalidraw/excalidraw-2024-11-07-14.18.21.excalidraw]]

The energy analysis for the control volume when considering the boundary drawn above is:

$$\cancel{\frac{dE}{dt}} = \cancel{\dot Q_{cv}} + \dot W_{cv} + \dot m (h_1+h_3)-\dot m(h_2+h_4)$$

$$\dot W_{cv} = \dot m (h_2+h_4-h_1-h_3)$$

This is a convenient way to get the net work without having to analyze each component.

> This concept of drawing the system boundary around both the turbine and the compressor can greatly reduce the amount of math needed.


