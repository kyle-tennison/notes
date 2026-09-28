# Quadratic Programming

This is a kind of optimization technique that takes $n$ variables with $m$ constraints to solve a problem.

Let
- $\mathbf c$ be a real vector of size $1 \times n$ that contains the $n$ variables.
- $Q$ be a real symmetric matrix of size $n \times n$ 
- $A$ be a real matrix of size $m \times n$ 
- $\mathbf b$ be a real vector of size $1 \times m$ that contains the constraints.

The optimization is minimizing:

$$\min \left[\frac 12 \mathbf x ^{\rm T}Q\mathbf x + \mathbf c^{\rm T}\mathbf x\right]$$

with the constraints:

$$A\mathbf {x} \preceq \mathbf {b}$$
The constraints are *linear inequality* constraints. 

---

## Linear Example

$$\max_{x\in \mathbb R, y\in \mathbb R} x+y$$

Subject to the constraints:
$$
\begin{gather}
x,y\ge 0\\
3x+2y \le 18\\
-x+2y \ge 2\\
x \le 3
\end{gather}
$$

Gives a "feasible region" that looks like this:

![[image-149.png|252]]

Then, if you draw a line $x+y=k$ and increment $k$, you will get lines increasing like this:

![](excalidraw-2026-09-21-18.43.13.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-09-21-18.43.13.excalidraw.md)%%

At some point, the line will no longer fit in the bounds; this the optimal solution at $(0,9)$.

## Quadratic Example

If you take the same problem as above but instead use:

$$x^2+y^2=k$$

You will get an incrementing circle like this:

![[image-151.png|308]]

At $b=81$, $k$ reaches the maximum value, and the optimal solution is $(0,9)$.


## References
- https://en.wikipedia.org/wiki/Quadratic_programming
- https://www.youtube.com/watch?v=yuGaGCoEP9E