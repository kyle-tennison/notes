# Sum Rule

The product rule states that, for a function $k(x) = f(x)+g(x)$:

$$\frac{dk}{dx}(f(x) + g(x)) = f'(x) + g'(x)$$

Now, let's write this in the limit definition:

$$\frac{dk}{dx}=\lim_{h\to 0} \frac{\big[ f(x+h)+g(x+h) \big] - 
\big[f(x)+g(x)\big]}{h}$$

Re-arranging terms easily shows how the 

$$\frac{dk}{dx}=\lim_{h\to 0} \frac{\big[ f(x+h)-f(x) \big] + 
\big[g(x+h)-g(x)\big]}{h}$$

$$\frac{dk}{dx}= \lim_{h\to 0} \frac{\big[ f(x+h)-f(x) \big]}{h}+ \lim_{h\to 0} \frac{ 
\big[g(x+h)-g(x)\big]}{h}=\frac{df}{dx}+\frac{dg}{dx}$$


We can also think about this more conceptually:

What we are doing is stepping over on the $x$ axis by $h$ to get the new value of our summation function. The partition that is $f$ has changed slightly, and so has the partition that is $g$. You can see that, this total ∆h is simply ∆f + ∆g. Shrink the ∆ until infinitesimal and you have you derivative.
