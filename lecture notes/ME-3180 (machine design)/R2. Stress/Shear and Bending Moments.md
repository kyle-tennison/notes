# Shear and Bending Moments


## Shear and Bending in Beams

Covered mostly in [Beams](Beams.md).

The premise is that, if the beam is cut at any point, the internal forces must act on the remaining body to ensure equilibrium. This breaks down into two components: a bending moment and a shear moment. 

Let $q$ be a function of $x$ along the beam called the **load intensity**, in units of force per unit length. The relationship for shear is then:

$$\frac{dV}{dx} = q$$
More commonly, we want to *find* the shear $V$ from $q$; we can do this by with:

$$V(x)-V(x_0) = \int_{x_0}^xq\;dx$$

which is from the [Fundamental Theorem of Calculus](Landau%20Video%202%20Script.md#^fundamental-theorem-of-calc), giving:

$$\boxed{V(x) = \int_{x_0}^{x} \;q(\tilde x)\;d\tilde x +V(x_0)}$$

A similar relationship exists for the bending moment, where $V=dM/dx$. Following similar calculus gives:

$$\boxed{M(x) = \int_{x_0}^xV(\tilde x) \;d\tilde x +M(x_0)}$$


## Singularity Functions

In beams there are often discontinuities in the applied loads and moments. For instance:

![](excalidraw-2026-01-19-17.06.14.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-01-19-17.06.14.excalidraw.md)%%
^sample-discrete-load

However this is not the only type:

![[image-80.png]]

^shingley-singularity-func-table

> From Shingley's 11th edition p. 98


For the discrete load I drew above, we could solve the "concentrated force" or "unit impulse" problem with something like this. Let $a=3 \rm m, b=5 \rm m, P=10\rm N$. 

```python
a = 3
b = 5 
P = -10

# Balance of forces for reaction in Y
R = -P

x = sp.symbols("x")

# We can geometrically find the shear with cross sections. We'll find that the shear is equal to the reaction while *left* of the applied force, and it will be zero to the *right* of the applied force. This is true specifically for this problem and should not be attempted elsewhere. 

V = sp.Piecewise(
	(0, x < 0),
	(R, x < a),
	(0, x < a+b),
	(0, True)
)

# Then we integrate this to get the moment. However, we don't know the moment at x_0 yet, so we define M_0
M0 = sp.symbols("M_0")

M = sp.integrate(V, (x,0,x)) + M0 

# Because we know that there is no shear at the end of the beam, we can solve this equation for M_0

sol = sp.solve(
	sp.Eq(M.subs(x, a+b), 0),
	M0
)

M = M.subs(M0, sol[0]) # then we update M with the new solution

# then some plotting stuff
p1 = sp.plot(V, (x,0,a+b), label="$V(x)$")
p2 = sp.plot(M, (x,0,a+b), label="$M(x)$")
p1.extend(p2)
p1.legend = True
p1.title = "Geometric Method"
p1.ylabel = ""
p1.save("media/ME-3180-demo1.png")
```

![](ME-3180-demo1.png)

---

Now, instead of relying on piecewise functions, we use the singularity functions. The base function is the **unit step function**:


$$\mathscr U(x-a) \equiv \langle x-a \rangle ^0$$

These are two different notations of the same thing. I note the $\mathscr U$ notation because this is what I learned in a pervious class.

Taking the derivative of the unit step function gives the **unit impulse function** $\langle x -a \rangle ^{-1}$ which is an impulse that spikes to $\infty$ at $x=a$ and is zero for the rest of the domain.

![](https://upload.wikimedia.org/wikipedia/commons/b/b4/Dirac_function_approximation.gif)


Taking the derivative again gives the **unit doublet** function, which "spikes" to $\pm \infty$ at $x=a$ and is zero for the rest of the domain. This one is the hardest to visualize, it can be thought of as this:

![|335x264](https://upload.wikimedia.org/wikipedia/commons/a/aa/UnitDoubletApproximationHighQuality.gif)

The positive portion corresponds to the upwards slope of the unit impulse. Here's a python script that might prove to be useful:

```python
x = sp.symbols("x")
k = 0.2 # As this -> 0, it becomes more accurate

dirac = 1 / (2*k) * sp.exp(-x**2/k) # unit impuse

unit_doublet = sp.diff(dirac, x)

unit_step = sp.integrate(dirac, (x, -sp.oo, x))

unit_ramp = sp.integrate(unit_step, (x, -sp.oo, x))

p1 = sp.plot(dirac, (x, -4, 4), label="Unit Impulse", show=False)
p2 = sp.plot(unit_doublet, (x, -4, 4), label="Unit Doublet", show=False)
p3 = sp.plot(unit_step, (x, -4, 4), label="Unit Step", show=False)
p4 = sp.plot(unit_ramp, (x, -4, 4), label="Unit Ramp", show=False)

p1.extend(p2)
p1.extend(p3)
p1.extend(p4)

p1.legend = True
p1.ylabel = ""
p1.title = "Singularity Functions"
p1.save("media/ME-3180-demo2.png")
```

![](ME-3180-demo2.png)

We can see how these are all related by derivatives. 

---

Now, we can solve the same [sample problem](#^sample-discrete-load) as before with this new technique. The load $p$ is a unit *impulse* function at $x=a$. We will again let $a=3 \rm m, b=5 \rm m, P=10\rm N$. 

The load can be described by:


$$
q(x) = R\langle x-x_0\rangle^{-1} -P\langle x - a \rangle^{-1} =10N \langle x-0\text m\rangle^{-1} -10{\rm N} \langle x - 3\text m\rangle^{-1}
$$

First, we need to define the reaction $R$. This can be done with a simple sum of forces:

$$\sum F _y = R- P = 0 \qquad \Rightarrow R=P=10\text N$$

Then, we can solve for the shear with the following (assuming $x_0 = 0$):

$$
\begin{aligned}
V(x) &= \int_{x_0}^x q(\tilde x) \,d\tilde x +V(x_0) = 10\text N \left[ 
\int_{x_0}^x\langle x - 0\text m\rangle^{-1} \,dx- \int_{x_0}^x \langle x - 3\text m\rangle^{-1}\,dx \right ]+ V(x_0) \\\\
&= 10\text N  \left[ \left[\langle x-0\text m \rangle ^0\right]^x_{x_0}- \left [ \langle x - 3\text m\rangle ^0 \right ]^x_{x_0} \right] +V(x_0)\\\\
&= 10\text N \left( \langle x - 0\text m \rangle ^0 - \underbrace{\langle 0\text m-0\text m\rangle^0}_{\text{\scriptsize Note Below*}} \right) -10\text N \left( \langle x - 3\text m \rangle ^0 - \langle 0\text m-3\text m\rangle^0 \right)  +V(x_0)
\end{aligned}
$$


When evaluating $\langle 0\text m-0\text m\rangle^0$ we need to be careful; this occurs right at the boundary of the $\delta$ function. Technically, our integration bounds $[x_0, x]$ kind of "cut off" the impulse right at its peak, where it's technically undefined. So instead, we'll lower our lower bound $x_0$ to $0^-\text m$ which is technically $< 0 \text m$. Therefore, $\langle 0^-\text m-0\text m\rangle^0 = 0$.

> On a more general note, I think you can in general get away with ignoring the lower bound, because I cannot imagine a scenario where it is helpful to consider the lower bound. I think you're technically supposed to be solving for arbitrary constants instead of using definite integrals anyways. 

If we only consider the domain where $x \in (0,\infty)$, we can cancel out the following terms:

$$
\begin{aligned}
&= 10\text N \left( \cancelto{1}{\langle x - 0\text m \rangle ^0 }- \cancelto{0}{\langle 0^-\text m-0\text m\rangle^0} \right) -10\text N \left( \langle x - 3\text m \rangle ^0 - \cancelto{0}{\langle 0\text m-3\text m\rangle^0} \right)  +V(x_0)\\\\
&=10N-10 \text N \langle x - 3\text m\rangle^0+V(x_0)
\end{aligned}
$$

Then, from the [singularity functions table](#^shingley-singularity-func-table) we can expand the step function $\langle x - 3 \text m \rangle ^0$ to:

$$\langle x - 3 \text m \rangle ^0 = \begin{cases}
0 & x<3\text m,\\
1 & x \ge 3 \text m
\end{cases}$$

Then, we have:

$$V(x) = 10\text N+V(x_0)-\begin{cases}
0 & x < 3 \text m,\\
10 \text N & x \ge 3 \text m
\end{cases}$$
At $x>a=3\text m$, we know that $V=0$ by inspection. This gives:

$$V(3^+\text m) = 0= 10\text N + V(x_0) - 10\text N, \qquad \Rightarrow V(x_0)=0$$

Therefore the answer is:

$$V(x) = 10 \text N - \begin{cases}
0 & x < 3 \text m,\\
10 \text N & x \ge 3 \text m
\end{cases}$$

Which agrees with the shear we had before.
