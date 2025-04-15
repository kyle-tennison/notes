# Chain Rule

### Function Composition

This is when the parameter of a function is a function itself—i.e., $f(g(x))$, or something equivalent.

If we want to take the derivative of a function that composes two other functions, it is nontrivial to solve with the [Sum Rule](Sum%20Rule.md) and [Product Rule](Product%20Rule.md). A new rule is needed.

## Derivation

Let our function $f(x)=g(h(x))$. We are interested in finding $f'(x)$.

When we vary $x$ by $dx$, $h$ varies by $dh$.

$$dh = h'(x)dx$$

Now, when we vary $h$ by $dh$, the exact same thing happens to $g$, except $dx$ is replaced by $dh$:

$$dg = g'(h)dh$$

If we substitute the prior expression for $dh$ here, we get:

$$dg = g'(h)h'(x)dx$$

Then, dividing by $dx$ gives:

$$\frac{dg}{dx}=g\big'(h(x)\big)h'(x)$$