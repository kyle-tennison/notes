# Euler's Method

We can discretize a continuous function using Euler's method:

$$v(t+∆t) = v(t) + f(v, t) \cdot ∆t$$

where:

$$f = \frac{v(t+∆t)-v(t)}{∆t}$$

which is the discretized derivative of $v$. Remember that the limit definition of a derivative is:

$$f=\lim _{∆t \to 0} \bigg[ \frac{v(t+∆t)-v(t)}{∆t} \bigg] $$