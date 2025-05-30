# Generalized Momentum Conservation Principle

From [Newton's Second Law](Galileo's%20Relativity%20Principle.md#^newtons-second-law), we know:

$$\textbf{F}=m\boldsymbol{\ddot x}$$

And from the [Conservation of Momentum](Conservation%20Laws.md#Momentum), we know:

$$\textbf{p} = m \boldsymbol{\dot x}$$

Hence, the time derivative of momentum is:

$$\boldsymbol{\dot p} = m \boldsymbol{\ddot x}$$

So, it can be said that **Force is the first time-derivative of Momentum**; that is:

$$\textbf{F} = \boldsymbol{\dot p}$$

Then, by integrating both sides, we get:

$$\int\limits_t^{t+\Delta t}\textbf{F}(t')\;dt'=\int\limits_t^{t+\Delta t}\boldsymbol{\dot p}(t')\;dt'$$

Because the average force $\bar{\boldsymbol{F}}$ is defined as $\bar{\boldsymbol{F}} = \frac{1}{\Delta t}\int\limits_t^{t+\Delta t}\textbf{F}(t')\;dt'$, the left-hand side of the equation can be replaced with $\bar{\boldsymbol{F}}\cdot \Delta t$. The right-hand side then integrates to $\textbf{p}(t+\Delta t)-\textbf{p}(t)$. In all, this becomes:

$$\Delta t\cdot \bar{\boldsymbol{F}}=\textbf{p}(t+\Delta t)-\textbf{p}(t)$$

This is known as the **Generalized Momentum Conservation Principle**