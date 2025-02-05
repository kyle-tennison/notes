# Root Finding


## Open Methods

### Fixed-Point Iteration

We want to find a function that gives:

$$x_{i+1}=g(x_i)$$

For instance, if we have something like:

$$f(x)=x^2-2x+3=0$$

We can move x to one side such that we have something like:

$$x=\frac{x^2+3}{2}$$

Now, using this, you can test values of $x$; if both sides are equivalent, then that $x$ is a root.

So, to summarize:
1. Start with a random value $x$; this is your guess
2. Plug this into $g(x_i)$
3. Plug the output of $g(x_i)$ back into $g$ and keep doing this until $x_i - x_{i-1}$ is small enough



