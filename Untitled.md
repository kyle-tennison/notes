# Untitled
**Knowns and sign convention:**

- \( x \) to the right is positive. The slider A is at \( x = x_A \) (negative), moves only horizontally.

- Flywheel center at \( O = (0,0) \). Crank \( OB = r \), with angle \( \theta \) measured from the \( +y \) axis. For \( \theta = 0^\circ \), \( B \) is at the top.

- Given at \( \theta = 0^\circ \): \( v_A \) to the left \( \Rightarrow \dot{x}_A = -v_A \), and \( a_A \) to the right \( \Rightarrow \ddot{x}_A = +a_A \).

---

**Geometry (constant length \( AB = l \)):**

Let \( B = (r\sin\theta, \; r\cos\theta) \) and \( A = (x_A, 0) \). Then

\[

(x_A - r\sin\theta)^2 + (r\cos\theta)^2 = l^2

\]

\[

\Rightarrow x_A^2 - 2x_A r\sin\theta + r^2 = l^2 \hspace{1cm} (1)

\]

From (1) at \( \theta = 0 \):

\[

x_A^2 + r^2 = l^2 \implies x_A = -\sqrt{l^2 - r^2} \hspace{1cm} (2)

\]

---

**Differentiate (1):**

\[

x_A \dot{x}_A - \dot{x}_A r\sin\theta - x_A r\cos\theta \dot{\theta} = 0

\]

At \( \theta = 0 \):

\[

x_A \dot{x}_A - x_A r \dot{\theta} = 0 \implies \dot{x}_A = r \dot{\theta} \implies \dot{\theta} = -\frac{v_A}{r} \hspace{1cm} (3)

\]

---

**Differentiate the first-derivative relation again:**

\[

\dot{x}_A^2 + x_A \ddot{x}_A - \ddot{x}_A r\sin\theta - 2\dot{x}_A r\cos\theta \dot{\theta} + x_A r\sin\theta \dot{\theta}^2 - x_A r\cos\theta \ddot{\theta} = 0

\]

At \( \theta = 0 \), and using (3):

\[

x_A \ddot{x}_A - r^2 \dot{\theta}^2 - x_A r \ddot{\theta} = 0

\]

\[

\Rightarrow \ddot{\theta} = \frac{\ddot{x}_A}{r} - \frac{r \dot{\theta}^2}{x_A} \hspace{1cm} (4)

\]

Insert \( \ddot{x}_A = a_A \), \( \dot{\theta} = -\frac{v_A}{r} \), and \( x_A \) from (2):

\[

\ddot{\theta} = \frac{a_A}{r} - \frac{r (v_A^2/r^2)}{-\sqrt{l^2 - r^2}}

\]

\[

= \frac{a_A}{r} + \frac{v_A^2}{r \sqrt{l^2 - r^2}}

\]

---

**Answer:**

- *Angular velocity at \( \theta = 0 \):*

\[

\omega = \dot{\theta} = -\frac{v_A}{r} \quad \text{(clockwise)}

\]

- *Angular acceleration of the flywheel:*

\[

\alpha = \ddot{\theta} = \frac{a_A}{r} + \frac{v_A^2}{r \sqrt{l^2 - r^2}}

\]

(positive in the CCW sense defined for \( \theta \)).