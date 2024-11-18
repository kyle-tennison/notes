# Exam Notes

The **mean effective pressure** (mep) is:

$$\frac{\dot W_{net}}{V_{disp}}$$

where:
- $\dot W _{net}$ is net power output
- $V_{disp}$ is the displacement volume (total change in volume)

You'll get units of something like $\frac{kJ}{m^3}$, which can then be converted into units of pressure.


The work for a control volume is not the same as the work for a closed system.

$$ \frac{\dot W_{cv}}{\dot m} = - \int \limits _1^2 v\ dp \tag{Control Volume}$$

$$W=  \int \limits_1^2 p \ dV \tag{Closed System}$$


### Isentropic Efficiencies

Isentropic turbine efficiency:
$$ \eta_t = \frac{\dot W_{cv}/\dot m}{(\dot W_{cv}/\dot m)_s}$$

Isentropic nozzle efficiency:

$$ \eta_{nozzle} = \frac{V^2_2/2}{(V^2/2)_s}$$

Isentropic compressor efficiency:

$$ \eta_c = \frac{(- \dot W_{cv}/\dot m)_s}{- \dot W_{cv}/\dot m}$$


### Ericsson Cycle

Ericsson cycle work uses the flow work integral;

$$ \dot W_t = -\dot m \int \limits _1^2 v\ dp$$

For an *ideal gas*, this can be expressed as:

$$-\dot m \int \limits _1^2 v\ dp = -\dot m R T_1 ln \frac{p_2}{p_1}$$



## Problems to Retry

- 8.20.13
- 8.20.59 (exit velocity)
- 8.20.69 (work)
