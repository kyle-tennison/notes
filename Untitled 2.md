Step (1) and (2) are perfectly acceptable; the difficulty enters when you try to impose the kinematic constraint on point C.

1. You wrote

$$\mathbf V_P = [-R\,\dot\theta,\;0]^T$$

for the point that is pinned to the rotating bar R.

At the “top-of-the-circle’’ position this is correct (the velocity of P is purely horizontal).

2. You then related the collar point C on bar B to P with the standard rigid-body formula

$$\mathbf V_C = \mathbf V_P + \boldsymbol\omega_{B}\times\mathbf r_{C/P},$$

which is also correct.

3. The error appears in the very next line, when you state

$$\mathbf V_C = V_C\,[\cos\theta,\;\sin\theta]^T\;.$$

This implicitly assumes that

a) C is rigidly attached to body L (pivoted at D), and

b) therefore C must move on a circle of radius \lVert D C\rVert about D, so its velocity must be

perpendicular to DC ( i.e. tangent to that circle).

Neither statement is true for this mechanism:

• The phrase “bar B slides through a collar in body L’’ means the collar **is fixed in L but the pin on B is free to slide in that collar**.

Consequently point C is *not* a permanent material point of body L; it can move **along the slot direction** with respect to L.

• Because C is free to slide, its distance to the lower pivot D is *not* constant, so its absolute

velocity need not be perpendicular to DC; it will in general have both normal and tangential components with respect to D.

The correct constraint is

$$\bigl(\mathbf V_C-\mathbf V_{C/L}\bigr)\cdot\mathbf t_{\text{slot}} = 0,$$

i.e. the relative velocity of C with respect to body L is confined to the slot’s axis

( $\mathbf t_{\text{slot}}$ is a unit vector along the slot).

By replacing that real constraint with the “purely-tangential’’ one you reduced the system of

equations incorrectly and obtained

$$\omega_B=\dot\theta/11,$$

which is therefore not the angular velocity required by the mechanism.

In short, the mistake is the assumption that $\mathbf V_C$ must be tangent to the circle about D; the collar actually allows a radial component along the slot, so step (3) is the source of the error.


--- 

Here is the one place the logic breaks:

You wrote the kinematic constraint on the collar as

$$\mathbf V_{C}=V_{C}

\begin{bmatrix}

\cos\theta\\[4pt]

\sin\theta

\end{bmatrix},\qquad (\star)$$

i.e. you forced the **velocity of the point C that belongs to bar B** to be perpendicular to the line DC and therefore strictly tangent to the circle centred at D.

Why this is not correct

• The collar (the little rectangular sleeve sketched on body L) is rigidly attached to body L, so the point

$$C_L \in L$$

indeed moves on a circle about D; its velocity is

$$\mathbf V_{C_L}= \boldsymbol\omega_{L}\times\mathbf r_{C/D}$$

and is therefore perpendicular to DC.

• Bar B, however, is allowed to **slide axially through that collar**.

At every instant there is a material point of B (call it

$$C_B \in B$$) that happens to be sitting inside the collar, so its *position* coincides with that of \(C_L\).

But because the collar permits axial sliding, \(C_B\) can have an **additional component of velocity parallel to the axis of bar B**. Consequently

$$\mathbf V_{C_B} = \mathbf V_{C_L} + v_{\text{slide}}\,

\mathbf e_{B},$$

where $\mathbf e_{B}$ is a unit vector along bar B and

$v_{\text{slide}}$ (the relative speed of sliding) is in general non-zero.

The velocity of $C_B$ is therefore **not, in general, perpendicular to DC**.

Only its component perpendicular to the axis of B must match the corresponding component of $\mathbf V_{C_L}$.

By replacing the real constraint with equation $(\star)$ you eliminated that axial (sliding) component, so the system became over-constrained and the algebra drove you to the spurious result
$$

\omega_{B}= \frac{\dot\theta}{11}.

$$

In short, step (3) is the source of the mistake: the velocity you constrained to be tangential is the velocity of the wrong body (the point of B, not of L) and therefore should not, in general, be perpendicular to DC.

---

he required dollar-sign delimiters.

1. What was wrong

The line

$$

\mathbf{V}_{C} = V_C

\begin{bmatrix}

\cos\theta \\[4pt]

\sin\theta

\end{bmatrix}

$$

is the only step that is physically incorrect.

It forces the *material* point of bar $B$ that happens to be at $C$ to move **purely tangent to the circle centred at $D$**, i.e. to have no component along the radius $DC$.

Because the collar allows the pin of $B$ to *slide* inside body $L$, an axial component *is* possible, so that constraint must not be imposed.

2. “But if I drop it I get another unknown!”

Dropping the “purely-tangent’’ constraint does not leave you under-determined; it only makes you write the kinematics in the standard way for a pin-in-slot joint.

Let

$$

\mathbf{t} =

\begin{bmatrix}

\cos\theta \\[4pt]

\sin\theta

\end{bmatrix}

, \quad

\mathbf{n} =

\begin{bmatrix}

-\sin\theta \\[4pt]

\cos\theta

\end{bmatrix}

$$

be unit vectors along and perpendicular to body $L$ (the axis of the slot).

Introduce one scalar $v_s$ = sliding speed of the pin *along* the slot.

Now write the two admissible velocities of the spatial point $C$:

• on body $B$:

$$

\boxed{

\mathbf{V}_C^{(B)} = \mathbf{V}_P + \boldsymbol{\omega}_B \times \mathbf{r}_{C/P}

}

\tag{1}

$$

• on body $L$:

$$

\boxed{

\mathbf{V}_C^{(L)} = \boldsymbol{\omega}_L \times \mathbf{r}_{C/D} + v_s \mathbf{t}

}

\tag{2}

$$

(The fixed pivot $D$ is at rest, so $\mathbf{V}_D = 0$.)

3. The *real* joint constraint

A pin-in-slot removes **one** degree of freedom, namely the velocity component *normal* to the slot must be the same for the two bodies:

$$

\boxed{

\left( \mathbf{V}_C^{(B)} - \mathbf{V}_C^{(L)} \right) \cdot \mathbf{n} = 0

}

\tag{3}

$$

Equation (3) supplies one scalar relation; the component along $\mathbf{t}$ is *not* forced to match—that is exactly the sliding you were forbidding before.

4. Number of unknowns vs. equations

Unknowns:

$\omega_B, \; \omega_L, \; v_s$  (three scalars)

Equations:

• two components from (1) ⇒ $\mathbf{V}_C^{(B)}$

• two components from (2) ⇒ $\mathbf{V}_C^{(L)}$

• one scalar constraint (3)

The three scalar *unknowns* appear only in

(1), (2), (3); from those five scalar relations you can eliminate the two components of $\mathbf{V}_C$, leaving exactly **three independent equations for the three unknowns**, so the system is determined.

(If you prefer, eliminate $v_s$ immediately by taking the dot-product with $\mathbf{n}$; you then have two equations in $\omega_B$ and $\omega_L$, again solvable.)

5. Bottom line

The mistake is **only** the step where you forced

$$

\mathbf{V}_C \parallel \mathbf{n} \quad \Longleftrightarrow \quad \mathbf{V}_C \cdot \mathbf{t} = 0.

$$

Replace that one scalar relation with the physically correct one, equation (3), and the velocity analysis closes without any contradiction or shortage of information.