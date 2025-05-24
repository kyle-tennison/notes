# Generalized Momentum Conservation Principle

From [Newton's Second Law](Galileo's%20Relativity%20Principle.md#^newtons-second-law), we know:

$$\textbf{F}=m\boldsymbol{\ddot x}$$

And, from the [Conservation of Momentum](Conservation%20Laws.md#Momentum), we know:

$$\textbf {p} = m \boldsymbol{\dot x}$$
Hence, the time derivative of momentum is:

$$\boldsymbol{\dot p} = m \boldsymbol{\ddot x}$$

So it can be said that **Force is the first time-derivative of Momentum**; that is:

$$\textbf{F} = \boldsymbol{\dot p}$$

Then, by integrating both sides, we get:

$$\int \limits _t^{t+\Delta t}\textbf{F}(t')\;dt'=\int \limits _t^{t+\Delta t}\boldsymbol{\dot p}(t')\; dt$$

Then, because the average force $\bar{\boldsymbol{F}} = \frac{1}{\Delta t}\int \limits _t^{t+\Delta t}\textbf{F}(t')\;dt'$, the LHS of the equation can be replaced with $\bar{\boldsymbol{F}}\cdot \Delta t$. Then, the LHS of the equation integrates to $\textbf{p}(t+\Delta t)-\textbf{p}(t)$. In all, this becomes;

$$\Delta\cdot \bar{\boldsymbol{F}}=\textbf{p}(t+\Delta t)-\textbf{p}(t)$$
This is known as the **Generalized Momentum Conservation Principle**