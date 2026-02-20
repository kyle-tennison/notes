# Partial Fraction Expansion

If a function $X(s)$ can be represented in the form of:

$$X(s) = \frac{N(s)}{D(s)}=\frac{b_ms^m+b_{m-1}s^{m-1}+\dots b_1s+b_0}{s^n+a_{n-1}s^{n-1}+\dots+a_1s+a_0}$$

and $m\le n$, then partial fractions can be conducted. 

> Notice how $a_n=1$. If this is not the case, you can divide $N$ and $D$ by $a_n$ to make it the case.


Now, we endeavor to find the roots of the denominator $D(s)$. 

## Real Roots

---
### Distinct Roots

When the denominator has only distinct roots, it can be factored in a form similar to:

$$X(s) = \frac{N(s)}{(s+r_1)(s+r_2)\cdots(s+r_n)}$$

Then, you can rewrite $X(s)$ like:

$$X(s) = \frac{C_1}{s+r_1}+\frac{C_2}{s+r_2}+\cdots+\frac{C_n}{s+r_n}$$
Then, you can solve for each $C_i$ using:

$$C_i = \lim_{s\to -r_i} \left[X(s)(s+r_i)\right]$$

> When you do this, the $(s+r_i)$ cancels out the denominator leaving $C_i$ for that term. All other terms gain $(s+r_i)$ terms, which then go to zero as the limit is taken.

### Repeated Roots

$$X(s) = \frac{N(s)}{(s+r_1)^p(s+r_2)\cdots(s+r_n)}$$


In the above equation, the $r_1$ root is repeated $p$ times, and the other roots remain real and distinct. In these cases, you add an extra term like so:

$$X(s) = \frac{C_1}{(s+r_1)^p}+\frac{C_2}{(s+r_1)^{p-1}}+\frac{C_3}{(s+r_1)^{p-2}}+\dots+\frac{C_{p+n}}{(s+r_n)}$$

To actually solve for these roots, you use:

$$
\begin{aligned}
C_1 &= \lim_{s\to-r_1}\left[ X(s)(s+r_1)^p \right]\\
\vdots\\
C_2 &= \lim_{s\to-r_1}\left\{\frac{d}{ds}\left[ X(s)(s+r_1)^p \right]\right\}\\
\vdots\\
C_i &= \lim_{s\to-r_1}\left\{\frac{1}{(i-1)!} \frac{d^{i-1}}{ds^{i-1}}\left[ X(s)(s+r_1)^p \right]\right\}, \qquad i=1,2,\dots,p
\end{aligned}
$$

---

For example (from ex. 3.5.3):

$$\frac{5}{s^2(3s+12)}=\frac13 \frac{5}{s^2(s+4)}= \frac{C_1}{s^2}+\frac{C_2}{s}+\frac{C_3}{s+4}$$

To solve for the coefficients:

$$C_1 = \lim_{s\to0}\left[ \frac{5}{\cancel{s^2}(3\cancelto{0}{s}+12)} \cdot \cancel{(s)^2} \right] = \frac{5}{12}$$

$$\begin{aligned}
C_2&=\lim_{s\to-0}\left\{\frac{d}{ds}\left[
\frac{5}{\cancel{s^2}(3s+12)} \cdot \cancel{(s)^2}
\right]\right\} =
\lim_{s\to-0}\left\{\frac{d}{ds}\left[
\frac{5}{3s+12}\right]\right\} \\
&= \frac 53\lim_{s\to-0}\left\{\frac{d}{ds}\left[
\frac{1}{s+4}\right]\right\} =
\frac 53\lim_{s\to-0}\left[
-\frac{1}{(\cancelto 0{s}+4)^2} \right] \\
&= \frac 53 \left( - \frac{1}{16} \right) = -\frac{5}{48}
\end{aligned}$$

Then, $C_3$ can be solved like an distinct root:

$$C_3 = \lim_{s\to{-4}}\left[ \cancel{(s+4)} \cdot \frac13 \frac{5}{\cancelto {-4^2}{s^2}\cancel{(s+4)}} \right] = \left(\frac 13\right) \left(\frac{5}{16}\right) = \frac{5}{48}$$

## Complex Roots

---

helll no