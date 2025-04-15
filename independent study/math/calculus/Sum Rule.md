# Sum Rule

The sum rule states that, for a function k(x) = f(x) + g(x):

$$\frac{dk}{dx}(f(x) + g(x)) = f'(x) + g'(x)$$

Now, let's write this in the limit definition:

$$\frac{dk}{dx}=\lim_{h\to 0} \frac{\big[ f(x+h)+g(x+h) \big] - \big[f(x)+g(x)\big]}{h}$$

Rearranging terms easily shows that

$$\frac{dk}{dx}=\lim_{h\to 0} \frac{\big[ f(x+h)-f(x) \big] + \big[g(x+h)-g(x)\big]}{h}$$

$$\frac{dk}{dx}= \lim_{h\to 0} \frac{\big[ f(x+h)-f(x) \big]}{h}+ \lim_{h\to 0} \frac{\big[g(x+h)-g(x)\big]}{h}=\frac{df}{dx}+\frac{dg}{dx}$$

We can also think about this more conceptually:

What we are doing is stepping along the x-axis by h to get the new value of our sum function. The partition corresponding to f has changed slightly, and so has the partition corresponding to g. You can see that this total Δ is simply Δf + Δg. Shrink the Δ until it is infinitesimal, and you have your derivative.