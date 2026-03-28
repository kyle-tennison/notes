# R4b. Stresses & Concentrations

## Direct Bearing

Bearing failure is when two surfaces being pressed together fail. This will crush/stretch the pin/hole instead of directly shearing it off. To calculate the bearing stress, you use the *projected area of contact* in the direction of applied stress. For a circle that is:

$$A_\text{bearing} = ld$$

where $l$ is the length of the contact and $d$ is the diameter of the hole/pin (whichever you are analyzing). 

## Tearout Failure

![[image-108.png|446x420]]

If a hole is placed too close to the edge of a part, tearout failure becomes a concern. This is a type of shear failure, because the mass under the pin is only held on with shear. 

![](excalidraw-2026-02-22-19.00.04.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-02-22-19.00.04.excalidraw.md)%%

The total area of tearout, labeled "tearout areas" above, is:

$$A_{\rm tearout} = t\left (R- \frac d2\right)$$

this is actually the *reduced area of shear*, which is slightly conservative, but generally easier to calculate.

## Stress Concentrations
### Photoelastic Analysis

**Photoelastic** analysis is when you make a part out of a iridescent plastic, then deform it. You can see how stress concentrations arise with this method.

![[image-106.png]]

The **stress-raiser** refers to the geometric artifact that causes the stress concentration, such as a notch or fillet. 
### Stress Concentration Factors

The stress concentration for any particular body is given by

$$\begin{gather}
\sigma_\max = K_t \sigma_\text{norm}\\
\tau_\max = K_{ts}\tau_\text{norm}
\end{gather}
$$

where $K_t$ and $K_{ts}$ are the stress-concentration factors for normal and shear stresses, respectively. 

#### Ductile Materials

Ductile materials will yield around the stress concentrator, but the rest of the material will remain below yield. For this reason, *stress concentrations can usually be ignored in ductile materials* under static loading. However, the reduction in area or moment of inertia due to the removed material should be accounted for. 

However, under **dynamic loading**, ductile materials will behave as if they were brittle. For this reason, the stress concentration factors should always be applied in dynamic loading, regardless of the material's ductility. 
#### Brittle Materials

These do not yield locally, instead they fracture locally at the stress concentrator. This crack often propagates easier than the stress-raiser itself, so the material will quickly experience catastrophic failure. 

One exception is porous cast materials that have many stress concentrations to start. Published stress/strain data will include this influence already, so we can often neglect the stress concentration if it is similar in size to the natural pores.

### Determining Stress-Concentration Factors

#### Semi-Infinite Plate

When the hole in a plate is negligibly small compared to the rest size of the rest of the plate, we call it "semi-infinite." If this plate is loaded in tension like shown below, stress concentration factor is:

![](excalidraw-2026-02-22-18.04.26.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-02-22-18.04.26.excalidraw.md)%%

We can see that as the hole gets sharper/flatter (i.e. $c/a \to 0$), the stress concentration factor goes to $\infty$. 









