# Multivariable Calculus

### Properties of Multivariable Limits

If we assert that $L$ and $M$ are *real numbers*:

$$\lim_{(x,y)\to (a,b)}f(x,y) = L \text{\;\;\;and\;\;\;}\lim_{(x,y)\to (a,b)}g(x, y) = M$$

We can state the following: 

| Identity Name         | Identity                                                                                         |
| --------------------- | ------------------------------------------------------------------------------------------------ |
| Constant Law          | $$\lim_{(x,y)\to (a,b)}c = c$$                                                                   |
| Identity Laws         | $$\lim_{(x,y)\to (a,b)} x = a \text{\;\;\;and\;\;\;}\lim_{(x,y)\to (a,b)}y = b$$                  |
| Sum Law               | $$\lim_{(x,y)\to (a,b)} \big(f(x,y) + g(x,y)  \big) = L+M$$                                      |
| Difference Law        | $$\lim_{(x,y)\to (a,b)} \big(f(x,y) - g(x,y)  \big) = L-M$$                                      |
| Constant Multiple Law | $$\lim_{(x,y)\to (a,b)}  \big ( c\cdot f(x,y)\big ) = cL$$                                       |
| Product Law           | $$\lim_{(x,y)\to (a,b)} \big( f(x,y)g(x,y)\big ) = LM$$                                          |
| Quotient Law          | $$\lim_{(x,y)\to (a,b)} \bigg(\frac{f(x,y)}{g(x,y)}\bigg ) = \frac{L}{M} \text{\;\;(for M ≠0)}$$ |
| Power Law             | $$\lim_{(x,y)\to (a,b)} \big (f(x,y)\big)^n = L^n$$                                              |

To be more pragmatic, if we have a large function $f$, we can use the *sum and difference laws* to break it apart at every $+$ and $-$ operator. We can also separate arbitrary constants using the *constant multiple law*.

**A limit only exists if it also exists for every path to the point.** For instance, if we are taking $\lim_{(x,y) \to (0, 0)}$, if we travel along $x=0$ or $y=0$ (or some other path) and find that the limit does not exist, we say that the multivariable limit does not exist either.

## Partial Derivatives

The limit definition for a partial derivative is as follows:

Let $f = f(x_0, x_1, \dots)$, and assume that $f$ is continuous on $\mathbb R^2$. 

$$\frac{\partial f}{\partial x_0} = \lim_{h\to 0}\frac{f(x_0+h, x_1, \dots)-f(x_0,x_1, \dots)}{h}$$

What we are doing here is watching how $f$ changes relative to $x_0$. All other $x_n$ are not changed. Because we are only examining the change in a single dimension, the quantities $x_n$ of higher dimensions *are constant*—i.e. *all variables that are not being differentiated with respect to are treated as constants.* 

Now, let $f=3yx$. If we substitute this into the limit definition above, we get:

$$\frac{\partial f}{\partial x}=\lim _{h\to0}\frac{3y(x+h)-3yx}{h}= \frac{\cancel{3yx}+3yh-\cancel{3yx}}{h}=3y$$

Because $y$ is not influenced by the $+h$ term, it is *identical* to a constant in single-variable differentiation. The rigorous proof for this theorem is, I imagine, much more complex; however, I'm satisfied with this explanation.

### Higher Order Partial Derivatives

Consider now that we want a second or nth order partial differential equation.

Before solving this mathematically, let's think about it for a second. When we solve for a partial differential equation, we get back another multivariable function that represents how the function changes with respect to a change in one of the independent variables. There is no reason we can't take the derivative of this new multivariable function of equal dimension in the same way as we did the first time:

$$\frac{\partial^2f}{\partial x^2}= \frac{\partial }{\partial x}\bigg(\frac{\partial f}{\partial x}\bigg)$$

Sometimes, this will be represented as $f_{xx}$ to show the second order differentiation with respect to x. If we, instead, had:

$$\frac{\partial^2f}{\partial y \ \partial x}= \frac{\partial }{\partial y}\bigg(\frac{\partial f}{\partial x}\bigg )$$

the corresponding notation would be $f_{xy}$. 

## Chain Rule