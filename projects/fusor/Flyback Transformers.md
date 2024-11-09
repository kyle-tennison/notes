
Flyback transformers were developed in order to drive high voltage CRTs for early televisions. "Unlike conventional transformers, a flyback transformer is not fed with a signal of the same waveshape as the intended output current." (1)

## Principle

![|466](../../media/Pasted%20image%2020241107204842.webp)

The primary side of the flyback transformer is *driven by a switched DC supply*.
> Would this be a square wave, does it depend?

While the switch is on, current begins to flow through the primary winding, as is shown above. The *inductance of the primary causes the current to ramp up*.

"An integral *diode connected in series with the secondary* winding prevents the formation of a secondary current that would eventually oppose the primary current ramp." (1) So you end up having an inductor, magnetically charged, with nothing else to induce an emf in. 

Then, the switch on the primary is opened and the current falls to zero. The **magnetic field around the primary quickly collapses**, creating a spike in magnetic flux rate, causing a sharp voltage spike in the secondary winding.

![](../../media/excalidraw/excalidraw-2024-11-07-20.55.35.excalidraw.svg)
%%[🖋 Edit in Excalidraw](../../media/excalidraw/excalidraw-2024-11-07-20.55.35.excalidraw.md)%%

The voltage spike rises until the load limits it, and then the current dies down like a ramp.

This cycle is repeated. If the current in the secondary drops to zero, the transformer is said to operate in *discontinuous mode*. If the current never reaches zero, then it's in *continuous mode*. 

### [Falstad Circuit POC](https://tinyurl.com/228kms9j)

![|576](../../media/Screenshot%202024-11-08%20at%209.34.08%20PM.png)


This not-so-realistic Falstad simulation shows how the secondary voltage can peak to insane values the moment after the switch is opened.  

## Physical Considerations






## References

1. [wikipedia](https://en.wikipedia.org/wiki/Flyback_transformer#History)