# Polar Calculus

Polar coordinates share the following relationship with ℝ² Cartesian coordinates:

| Cartesian        | Polar             |
| ---------------- | ----------------- |
| $x$              | $r\cos(\theta)$   |
| $y$              | $r\sin(\theta)$   |
| $\tan^{-1}(y/x)$ | $\theta$         |
| $\sqrt{x^2+y^2}$ | $r$               |

A polar coordinate *ordered pair* is arranged as $(r, \theta)$.

### Polar Coordinate Symmetry

1. If $r(\theta) \equiv r(-\theta)$, there is symmetry with respect to the polar axis (i.e., the axis on which $\theta = 0$ lies, usually $y=0$).
2. If $r(\theta) \equiv r(\theta + \pi)$, then for every $(r, \theta)$ there is a corresponding $(-r, \theta)$; this is symmetry with respect to the pole.
> 🤖 (notecheck comment) - In bullet 2, note that the standard representation is that (r, θ) is equivalent to (‑r, θ + π), not (‑r, θ). Adjusting the angle by π when switching the sign of r is necessary for accurately representing symmetry with respect to the pole.
3. If $r(\theta) \equiv r(\pi - \theta)$, then there is symmetry with respect to the $\theta = \pi/2$ axis.

![](../../../media/Pasted%20image%2020250112224050.webp)

## Polar Integration

![](../../../media/excalidraw/excalidraw-2025-01-12-22.44.26.excalidraw.svg)
%%[🖋 Edit in Excalidraw](../../../media/excalidraw/excalidraw-2025-01-12-22.44.26.excalidraw.md)%%

The differential element for a polar function is a triangle. The differential area of this triangle is:

$$dA = \frac{1}{2} \, d\theta \, r(\theta)^2$$

If we integrate both sides, we get:

$$A = \int \limits_{\theta_0}^{\theta_1} \frac{1}{2}r(\theta)^2 \, d\theta$$

#### Area Between Polar Curves

![](../../../media/excalidraw/excalidraw-2025-01-12-22.53.37.excalidraw.svg)
%%[🖋 Edit in Excalidraw](../../../media/excalidraw/excalidraw-2025-01-12-22.53.37.excalidraw.md)%%

If we want to find the area between two polar curves, we have to subtract the smaller area from the larger. Mathematically, this looks like:

$$dA = A_2 - A_1 = \frac{1}{2}\big[r_2^2 - r_1^2\big] \, d\theta$$

$$ A = \frac{1}{2} \int _{\alpha}^{\beta}\left(r_2^2(\theta) - r_1^2(\theta)\right) \, d\theta = A_2 - A_1$$

Note that $\alpha$ and $\beta$ are the angles at which the curves first intersect, as shown by the dotted lines in the diagram above.