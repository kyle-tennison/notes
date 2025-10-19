# Untitled

## Problem 1

GIVEN

- Right‑angle slender bar, equal legs $L$, mass $m$, pinned at $C$ to a plate accelerating right with $a$; pegs at $A,B$ prevent rotation.

FIND

- The $a$ for which pegs exert zero force.

ANALYSIS

Work in the non‑inertial frame attached to the plate. The bar does not rotate relative to the plate; apply d’Alembert force $-m a\,\hat{\mathbf{i}}$ at its mass center along with weight $-m g\,\hat{\mathbf{j}}$. For the pegs to be force‑free, the pin at $C$ must carry all reactions, and since the pin cannot supply a couple, the resultant of the applied forces must pass through $C$ (zero moment about $C$).

Centroid of the L-bar (two equal slender legs, each of mass $m/2$):

- Midpoint of horizontal leg: $(-L/2,\,0)$

- Midpoint of vertical leg: $(-L,\,-L/2)$

So

$$x_G=\frac{(-L/2)+(-L)}{2}=-\frac{3L}{4},\qquad

y_G=\frac{0+(-L/2)}{2}=-\frac{L}{4}$$

$$\mathbf{r}_G=(-\tfrac{3L}{4})\hat{\mathbf{i}}+(-\tfrac{L}{4})\hat{\mathbf{j}}$$

Zero moment about $C$:

$$\mathbf{M}_C=\mathbf{r}_G\times\left(-m a\,\hat{\mathbf{i}}-m g\,\hat{\mathbf{j}}\right)=0$$

$$\Rightarrow\; \frac{mL}{4}\,(3g-a)\,\hat{\mathbf{k}}=0 \;\Rightarrow\; a=3g$$

Therefore the plate must accelerate to the right with

$$\boxed{a=3g\;\text{(to the right)}}$$

## Problem 2

GIVEN

- Uniform rod, contacts at A (seat back, vertical) and at B (seat base, 7° pitch); rod is at $30^\circ$ from vertical; car decelerates with $a$.

FIND

- The deceleration $a$ at which the rod just tips forward.

ANALYSIS

Work in the car frame. At the tipping threshold the contact at A goes to zero; the rod will rotate about $B$. Reactions at $B$ pass through $B$, so take moments about $B$ of the real forces and the d’Alembert force. The 7° seat pitch is irrelevant for this moment balance.

For a uniform rod, $G$ is at mid‑length; from $B$ to $G$:

$$\mathbf{r}_{BG}=\frac{L}{2}\big(-\sin 30^\circ\,\hat{\imath}+\cos 30^\circ\,\hat{\jmath}\big)$$

Forces acting: weight $-mg\,\hat{\jmath}$ and inertial (d’Alembert) force $+m a\,\hat{\imath}$. Zero net moment about $B$:

$$M_B=\mathbf{r}_{BG}\times\big(m a\,\hat{\imath}-m g\,\hat{\jmath}\big)\cdot\hat{\mathbf{k}}=m\frac{L}{2}\Big(g\sin 30^\circ-a\cos 30^\circ\Big)=0$$

$$\Rightarrow\; a=g\tan 30^\circ$$

Numerically,

$$a=0.577\,g\approx 5.66\ \text{m/s}^2\ (\text{deceleration})$$

$$\boxed{a=g\tan 30^\circ\approx 5.66\ \text{m/s}^2}$$


## Problem 3

GIVEN

- A slender circular hoop (radius $r$, mass $m$) pinned at $O$ on its rim; torsional spring $k_T$ at $O$ twisted $90^\circ=\pi/2$ clockwise at release.

FIND

- Magnitude of the pin force at $O$ at the instant of release.

ANALYSIS

Take CCW positive. At the shown position the hoop’s mass center is at the circle center directly below $O$, so the weight line of action passes through $O$ and produces no moment about $O$ initially. The spring exerts a restoring couple $M_T=k_T(\pi/2)$, giving the initial angular acceleration from the moment equation about $O$.

Moment of inertia of a thin circular hoop about a point on its rim:

$$I_O=I_C+m r^2=m r^2+m r^2=2 m r^2$$

Initial angular acceleration:

$$\sum M_O = I_O \alpha \quad\Rightarrow\quad k_T\frac{\pi}{2}=2 m r^2\,\alpha

\;\Rightarrow\; \alpha=\frac{k_T\pi}{4 m r^2}$$

Acceleration of $G$ (with $\omega=0$ at release, purely tangential):

$$a_G=\alpha r=\frac{k_T\pi}{4 m r}$$

Translation of the hoop ($\sum \mathbf F=m\mathbf a_G$) with forces $\mathbf R_O$ at $O$ and weight $m\mathbf g$:

- Horizontal: $R_x=m a_G=\dfrac{k_T\pi}{4 r}$

- Vertical: $R_y-mg=0\;\Rightarrow\;R_y=mg$

Pin‑force magnitude:

$$R_O=\sqrt{R_x^2+R_y^2}

=\sqrt{\left(\frac{k_T\pi}{4 r}\right)^2+(m g)^2}$$

$$\boxed{\,R_O=\sqrt{\left(\dfrac{k_T\pi}{4 r}\right)^2+(m g)^2}\,}$$



## Problem 4

GIVEN

- Uniform slender right‑angle bar, total length $L$, mass $m$; pivoted at $O$; horizontal leg $3L/4$, vertical tip $L/4$; released from rest.

FIND

- Initial angular acceleration $\,\alpha\,$ and the magnitude of the pivot force at $O$.

ANALYSIS

Take $x$ right, $y$ up. Treat as two slender segments. Mass per length $\lambda=m/L$. Midpoints:

- Horizontal: $(x_h,y_h)=(\tfrac{3L}{8},0)$, mass $m_h=\tfrac{3m}{4}$

- Vertical: $(x_v,y_v)=(\tfrac{3L}{4},\tfrac{L}{8})$, mass $m_v=\tfrac{m}{4}$

Center of mass:

$$x_G=\frac{m_h x_h+m_v x_v}{m}=\frac{9+6}{32}L=\frac{15L}{32},\qquad

y_G=\frac{m_h y_h+m_v y_v}{m}=\frac{L}{32}$$

Moment of inertia about $O$ (sum of segments):

$$I_O=\underbrace{\frac{m_h}{3}\Big(\tfrac{3L}{4}\Big)^2}_{\text{horizontal}}

+\underbrace{\left[\frac{m_v}{12}\Big(\tfrac{L}{4}\Big)^2+m_v\Big((\tfrac{3L}{4})^2+(\tfrac{L}{8})^2\Big)\right]}_{\text{vertical}}

=\frac{55}{192}\,mL^2$$

Gravity acts at $G$: $\mathbf{W}=-mg\,\hat{\mathbf{j}}$. About $O$,

$$\sum M_O = \mathbf{r}_{OG}\times\mathbf{W}

= (x_G\hat{\mathbf{i}}+y_G\hat{\mathbf{j}})\times(-mg\hat{\mathbf{j}})

= -mg\,x_G\,\hat{\mathbf{k}}$$

Fixed pivot ⇒ $\sum M_O=I_O\alpha$:

$$-mg\Big(\frac{15L}{32}\Big)=\Big(\frac{55}{192}mL^2\Big)\alpha

\;\Rightarrow\;

\boxed{\;\alpha=-\frac{18}{11}\frac{g}{L}\;}\quad(\text{clockwise})$$

With $\omega_0=0$, $\,\mathbf{a}_G=\boldsymbol{\alpha}\times \mathbf{r}_{OG}$:

$$\mathbf{a}_G=\alpha\big(-y_G\hat{\mathbf{i}}+x_G\hat{\mathbf{j}}\big)

=\Big(\frac{9}{176}g\Big)\hat{\mathbf{i}}-\Big(\frac{135}{176}g\Big)\hat{\mathbf{j}}$$

Force balance on the body, $\mathbf{O}+\mathbf{W}=m\mathbf{a}_G$:

$$O_x=m a_{Gx}=\frac{9}{176}mg,\qquad

O_y=mg+m a_{Gy}=mg-\frac{135}{176}mg=\frac{41}{176}mg$$

Magnitude of the pivot force:

$$\boxed{\;|\mathbf{O}|=\sqrt{O_x^2+O_y^2}
=\frac{mg}{176}\sqrt{9^2+41^2}
=\frac{\sqrt{1762}}{176}\,mg\;\approx 0.239\,mg\;}$$


## Problem 5

GIVEN

- Slender horizontal rod, mass $m$, length $L$, hung by two vertical strings at ends $A$ (left) and right; right string is cut at $t=0$.

FIND

- Initial tension in the left string, $T_A(0^+)$.

ANALYSIS

Immediately after the cut the rod is still at rest ($\omega=0$) and the left end $A$ is on a taut vertical string, so its acceleration along the string is zero: $a_{A,y}=0$. External forces: $T_A$ at $A$ (upward) and $mg$ at $C$ (downward at $L/2$ from $A$). Take counterclockwise positive.

Sum of moments about $A$ gives the initial angular acceleration:

$$\sum M_A = I_A \alpha \quad\Rightarrow\quad -mg\left(\frac{L}{2}\right)=\left(\frac{1}{3}mL^2\right)\alpha$$

$$\Rightarrow\;\alpha=-\frac{3g}{2L}\;(\text{clockwise})$$

Acceleration of $G$ using $a_G=a_A+\alpha\times r_{G/A}$ with $\omega=0$:

$$a_{G,y}=a_{A,y}+\alpha\left(\frac{L}{2}\right)=0+\left(-\frac{3g}{2L}\right)\left(\frac{L}{2}\right)=-\frac{3g}{4}$$

Vertical force balance on the rod:

$$\sum F_y = m a_{G,y}\quad\Rightarrow\quad T_A-mg=m\left(-\frac{3g}{4}\right)$$

$$\Rightarrow\;T_A=\frac{mg}{4}$$

$$\boxed{T_A(0^+)=\dfrac{mg}{4}}$$


## Problem 6

GIVEN

- Cart $D$ accelerates right with $a$. Cylinder $C$: mass $m_c$, radius $r$, homogeneous.

FIND

- $a_C$ (acceleration of the cylinder’s center in the ground frame) and the friction $f$ on $C$ by $D$ (direction, magnitude).

- Minimum $\mu$ for no slip.

ANALYSIS

No slip between cylinder and cart, so the contact point on the cylinder has the same horizontal acceleration as the cart surface. Take +x to the right; in the inertial (ground) frame the only horizontal force on $C$ is friction $f$.

$$\sum F_x:\; f = m_c a_C$$

Moment about $C$ (counterclockwise positive), with $I_C=\tfrac12 m_c r^2$:

$$\sum M_C:\; f r = I_C \alpha = \tfrac12 m_c r^2 \alpha \;\Rightarrow\; \alpha=\frac{2f}{m_c r}$$

Kinematic no–slip at contact (horizontal component):

$$a_C + \alpha r = a$$

Substitute $\alpha$ and $f=m_c a_C$:

$$a_C + \frac{2f}{m_c} = a \;\Rightarrow\; a_C + 2a_C = a \;\Rightarrow\; 3a_C=a \;\Rightarrow\; a_C=\frac{a}{3}$$

Then

$$f=m_c a_C=\frac{m_c a}{3}\quad(\text{to the right}),\qquad

\alpha=\frac{2}{3}\frac{a}{r}\;(\text{CCW})$$

Friction condition $|f|\le \mu N$, with $N=m_c g$:

$$\mu_{\min}=\frac{f}{m_c g}=\frac{a}{3g}$$

$$\boxed{a_C=\dfrac{a}{3}\ \text{(right)}},\quad \boxed{f=\dfrac{m_c a}{3}\ \text{(right)}},\quad \boxed{\mu_{\min}=\dfrac{a}{3g}}$$