# Multivariable Chain Rule

Consider that we have a multivariable function $f(x,y)$. Say we also have two single-variable functions, $x(t)$ and $y(t)$, that we pass to $f$ such that we get $f(x(t), y(t))$. In this scenario, $f$ is now a single-variable function that depends on $t$. If we want to find its derivative with respect to $t$, we can substitute $x(t)$ and $y(t)$ into the function body and differentiate like any other ordinary derivative. However, we can simplify this into an expression called the **multivariable chain rule.**

Imagine what happens when we take the derivative of $x$ with respect to $t$:

$$\frac{dx}{dt} = \lim_{h\to 0}\frac{x(t+h)-x(t)}{h}$$

Then, by multiplying by $dt$, we get the definition of $dx$:

$$dx = x'(t) dt \tag{1}$$ 

The same can be done for $dy$:

$$dy = y'(t) dt \tag{2}$$

Now, we are interested in finding how $f$ varies with $t$. However, it's normally a function of both $x$ and $y$. So, instead of bringing $t$ into the picture, we can first focus on how $f$ would vary with $x$ and $y$.

$$df = \frac{\partial f}{\partial x}dx + \frac{\partial f}{\partial y}dy \tag{3}$$

The partial derivative $\partial f / \partial x$ gives us the change in $f$ per change in $x$. This change in $x$, for $df$, is $dx$. Similarly, $\partial f / \partial y$ gives the change in $f$ per change in $y$. By summing these two changes, we get the total change in $f$ for a change in $x$ and $y$. 

We can now substitute Eq. 1 and Eq. 2 into Eq. 3 to get:

$$df = \frac{\partial f}{\partial x}\frac{dx}{dt}dt + \frac{\partial f}{\partial y}\frac{dy}{dt}dt$$

Then, dividing by $dt$ gives us:

$$\frac{df}{dt} = \frac{\partial f}{\partial x}\frac{dx}{dt} + \frac{\partial f}{\partial y}\frac{dy}{dt} \tag{4}$$
^eq-4

## Vector Form

We can express [Eq. 4](#^eq-4) using a dot product:

$$\frac{df}{dt} = 

\begin{bmatrix}
\frac{\partial f}{\partial x} \\
\frac{\partial f}{\partial y}
\end{bmatrix}

\cdot 

\begin{bmatrix}
\frac{dx}{dt} \\
\frac{dy}{dt} 
\end{bmatrix}

\tag{5}
$$

If we make a [Vector Valued Function](Vector%20Valued%20Functions.md), instead of having two functions $x(t)$ and $y(t)$, we can say:

$$
\textbf{v} =
\begin{bmatrix}
x(t) \\
y(t) 
\end{bmatrix}
\text{\ \ \ and\ \ \ }

\textbf{v}' = 
\begin{bmatrix}
\frac{dx}{dt} \\
\frac{dy}{dt} 
\end{bmatrix}

\tag{6}
$$

Also, notice that the leftmost vector in Eq. 5 is simply the gradient of $f$:

$$\nabla f = 

\begin{bmatrix}
\frac{\partial f}{\partial x} \\
\frac{\partial f}{\partial y}
\end{bmatrix}$$

So, we can rewrite this entire equation generically as:

$$\frac{df}{dt} = \nabla f(\textbf{v}(t)) \cdot \textbf{v}'(t)$$

### References

```vid
https://www.youtube.com/watch?v=qZlBjnC3iro
Title: Vector form of the multivariable chain rule
Author: Khan Academy
Thumbnail: https://i.ytimg.com/vi/qZlBjnC3iro/mqdefault.jpg
AuthorUrl: https://www.youtube.com/@khanacademy
```