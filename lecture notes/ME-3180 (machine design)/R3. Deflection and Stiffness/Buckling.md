# Buckling

## Euler Buckling

Euler buckling is for long, slender rods with central loading. Other scenarios are discussed below.

### Derivation

![[image-95.png]]


Consider (a) above. The bending moment changes along the rod depend on how far it deviates from the $x$ axis. We can write this as:

$$M = -Py$$

where $P$ is the force applied at $y=0$. The bending bulges in the $+y$ direction, meaning we should expect the moment to be negative. We can also see, at around $x = l/2$, the force $P$ is separated by $y$ from the beam, which is where $M=-Py$ comes from. If the beam were to buckle in the opposite direction, the moment would be positive and $y$ would be negative, and the same equation would result. 


From [flexure](Flexure.md#^1f4f04) we know:

$$\frac{d^2y}{dx^2}= \frac{M}{EI}$$

Substituting in $M=-Py$ gives:

$$\frac{d^2y}{dx^2} + \frac{P}{EI}y=0$$

This has the format of the common differential equation:

$$y''+k^2y=0$$

which has the solution:

$$y= c_1 \cos(kx)+c_2\sin(kx)$$

> This is the same as a SHO and the 1D version of the "[Helmholtz Equation](https://en.wikipedia.org/wiki/Helmholtz_equation)"

In this context, $k=\sqrt{P/EI}$, so the solution is:

$$y=c_1\cos\left(x\sqrt{\frac{P}{EI}}\right)+c_2\sin\left(x\sqrt{\frac{P}{EI}}\right)$$

The boundary conditions *when both points are pinned* is $y(0)=0$ and $y(l)=0$. (Note: $y$ is a function of $x$ here). This gives

$$\begin{aligned}
y(0) &=0= c_1 \cancelto{1}{\cos(0)}+ \cancelto{0}{c_2\sin(0)}= c_1\\
0&=c_1
\end{aligned}$$

and

$$
\begin{aligned}
y(l)=0&=\cancelto{0}{c_1}\cos\left(l\cdot\sqrt{\frac{P}{EI}}\right)+{c_2}\sin\left(l \cdot \sqrt{\frac{P}{EI}}\right)
\\&=c_2\sin\left(l\cdot\sqrt{\frac{P}{EI}}\right)
\end{aligned}
$$
The trivial solution is $c_1=0$; however, forcing $c_1\ne0$ gives:

$$\begin{aligned}
0&= \sin\left({l\cdot\sqrt{\frac{P}{EI}} }\right)\\\\
l \cdot \sqrt{\frac{P}{EI}}&=n \pi,\quad \;n=1,2,3,\dots\\\\
\because\sin(x)&=0 \text{ only when } x \in \{\pi, 2\pi, 3\pi, \dots\}
\end{aligned}$$

Selecting $n=1$ gives the *first critical load*, which, when solved, gives:

$$\underset{\text{Only pin-pin columns!}}{{P_{\rm cr} = \frac{\pi ^2 EI}{l^2}}}$$
This pin-pin specific equation is known as the **Euler column formula**. However, it is expressed more generally with:

$$
\underset{\large \textbf{Generic Euler Buckling}}{\boxed{\large 
\frac{P_{\rm cr}}A = \frac{C\pi^2E}{(l/k)^2}
}} \tag{a}$$
^generic-euler-buckling

where $A$ is the cross-section area and $k$ is the [radius of gyration](https://en.wikipedia.org/wiki/Radius_of_gyration). You can find $k$ with:

$$k = \sqrt{\frac IA}$$
> Use the minimum $I$ when multiple are present, such as in an I-Beam.

The right hand side, $P_{cr}/A$ is the *unit load*—i.e., the maximum force per unit area that *a specific beam* beam handle. More on this below. The value $(l/k)$ is the **slenderness ratio**.

> Not sure why this confuses me, but a *larger slenderness ratio* means a *longer/thinner* beam.
### Euler Curve

The Euler Curve is obtained by plotting the [Euler Buckling](#^generic-euler-buckling) formula over a series of slenderness ratios. 

![[image-96.png]]

 If the unit load is selected to be the yield stress $S_y$, the corresponding "worst" (maximum) slenderness ratio is $(l/k)_Q$ .

$$\text{Unit load of } S_y \Rightarrow \left (\frac{l}{k} \right)_Q$$

But this honestly isn't very relevant; real beams usually fail much before $Q$. In general, a point $T$ is selected on the curve, and a the corresponding slenderness ratio is noted $(l/k)_1$.

> TODO: Update this above paragraph; misleading

The choice of $T$ is not rigidly defined; however, *a popular default* is to allow:

$$T = \frac{P_{\rm cr}}{A}\approx \frac{S_y}{2}$$

> By defining $T$, we're really just defining $P_{\rm cr}$ .

Under this choice of $T$, $(l/k)_1$ is defined as:

$$\left(\frac{l}{k}\right)_1 = \left(\frac{2 \pi^2 CE}{S_y} \right)^{1/2}$$
^T-slenderness-ratio-def

which is simply a substitution of the definition of $T$ into the [generic Euler buckling](#^generic-euler-buckling) equation (above).

### Effective Length Method

**This is the method used in class.**

A slightly different approach to this problem is to use the **effective length** $l_{\rm eff}$. 

$$l_{\rm eff} = Kl$$

where $K$ is the *effective length factor* and $l$ is the "real" length of the column. 

> I believe that $C = {1}/{K^2}$, just from inspection. This is "proved" below.


The equation is then:

$$P_{\rm cr} = \frac{\pi^2 EI}{(Kl)^2} = \frac{\pi^2 EI}{l_{\rm eff}^2} $$

If you divide $l_{\rm eff}$ by the radius gyration, we can define a variable $S_r$ (not sure what this means):

$$S_r = \frac{l_{\rm eff}}{k} \quad\underbrace{= \frac{Kl}{\sqrt{I/A}} = \frac{l\sqrt A}{\sqrt {CI}}}_{\text{using for verificaiton lower}}$$
^sr-def

This $S_r$ is also called the *slenderness ratio*, but is **not the same as** the "slenderness ratio" discussed elsewhere here, which is defined as $(l/k)$. The qualitative difference is that the $S_r$ slenderness ratio contains the knowledge of the beam-loading type; i.e., the $K$ or $C$ value is "build-into" it.

The reader then gives the following for Euler buckling:

$$\underline{\frac{P_{cr}}{A}= \frac{\pi^2 E}{S_r^2}} = \frac{\pi^2ECI}{l^2A} = \frac{\pi^2ECk^2}{l^2} = \frac{\pi EC}{(l/k)^2}$$

which matches the equation in my [Derivation](#Derivation) so these are indeed identical. So, these are just different ways of expressing the same thing.

### End-Condition Table

To select the value of $C$ in the above tables, use the following:

> I'm assuming that rounded is synonymous with pinned

From Singley's 8th Ed, the values of $C$ are given:

| Column End Condition | Theoretical Value | Conservative Value | Recommended Value |
| -------------------- | ----------------- | ------------------ | ----------------- |
| Fixed-free           | $1/4$             | $1/4$              | $1/4$             |
| Pined-Pined          | $1$               | $1$                | $1$               |
| Fixed-Pinned         | $2$               | $1$                | $1.2$             |
| Fixed-Fixed          | $4$               | $1$                | $1.2$             |

An alternative way to do this is to use the *effective length*. The ME-3180 reader gives these effective lengths $l_{\rm eff}$:

| Column End Condition | Theoretical Value | Conservative Value | Recommended Value (AISC) |
| -------------------- | ----------------- | ------------------ | ------------------------ |
| Fixed-free           | $2l$              | $2.4l$             | $2.1l$                   |
| Pinned-Pinned        | $l$               | $l$                | $l$                      |
| Fixed-Pinned         | $0.707l$          | LOST               | $0.80l$                  |
| Fixed-Fixed          | $0.5l$            | $l$                | $0.65l$                  |
| Rounded-Rounded      | $l$               | $l$                | $l$                      |
> Not sure how rounded-rounded differs from pinned-pinned

> If you divide these above values by $l$, the remaining scalar coefficient is $K$


![](excalidraw-2026-02-05-20.26.43.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-02-05-20.26.43.excalidraw.md)%%

Apply these with [Eq. (a)](#^generic-euler-buckling) above.

## Parabolic/Johnson Loading

Johnson Loading is for "intermediate" length columns. On the [Euler Curve](#Euler%20Curve), the dotted-line shows how Johnson loading differs from Euler loading. In this region, where $(l/k)<(l/k)_1$, we use this bending method. 

![[image-97.png]]

> This figure uses $S_{yc}$ instead of $S_y$ for yield stress. It also uses a slightly different definition of the slenderness ratio.

The equation is:

$$\underset{\large\textbf{Parabolic/Johnson Loading}}{\boxed{\frac{P_{\rm cr}}{A}= S_y- \left( \frac{S_y}{2\pi}\frac{l}{k} \right)^2 \frac{1}{CE}, \qquad \text{when } \frac{l}{k}\le \left(\frac{l}{k}\right)_1}}$$


From the machine design reader, this is instead given as:

$$\frac{P_{\rm cr}}{A} = S_{y} - \frac{1}{E}\left(\frac{S_{\rm y}\cdot S_r}{2\pi} \right)^2$$

From the definition of $S_r$ [above](#^sr-def), this expands to:

$$
\begin{aligned}
\frac{P_{\rm cr}}{A} &= S_{y} - \frac{1}{E}\left(\frac{S_{\rm y}\cdot S_r}{2\pi} \right)^2 = S_y - \frac 1E \left( \frac{S_y}{2\pi}\cdot \frac{l\sqrt A}{\sqrt {CI}} \right)^2\\
&=S_y - \frac 1E \left( \frac{S_y}{2\pi}\cdot \frac{l}{k\sqrt C} \right)^2\\
&= S_y - \frac 1{CE} \left( \frac{S_y}{2\pi}\cdot \frac{l}{k} \right)^2

\end{aligned} 
$$

so we can see that these are again equivalent. 

In the [Euler Curve](#Euler%20Curve) section, we used $(l/k)_1$ as the delimiter; however, if we are using the method that's provided from the reader, the delimiter is instead $(S_r)_D$:

$$(S_r)_D = \pi \sqrt{\frac{2\cdot E}{S_y}}$$
If $S_r > (S_r)_D$,  use the Euler method; otherwise, use the Johnson method. 



[^1]: p. 123, 5th ed