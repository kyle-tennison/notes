# Poisson's equation

Poisson's equation is generally:

$$\nabla ^2 \Phi = \sigma$$

where $\sigma$ is some forcing function. 

**Laplace's equation** is similarly defined, only with the constraint that $\sigma =0$;

$$\nabla ^2 \Phi =0 $$


## Finite Difference Method
### Boundary Condition Types
A **Dirichlet Boundary Condition**[^1] *fixes the solution* of a differential equation at the boundaries. These are called boundary conditions of the *first-type* For instance: 

$$y''+y=0$$
The boundaries would be:
$$y(a)=\alpha \quad \text{and}\quad y(b)=\beta$$

A **Neumann Boundary Condition**[^2] specifies the *derivative* of a differential equation at the boundary. For instance:

$$y''+y=0$$

The boundaries would be:

$$y'(a)=\alpha \quad \text{and}\quad y'(b)=\beta$$

### Numeric Derivatives

- The backward finite difference: $du/dt\approx (D^- u)_j=\frac{u_j-u_{j-1}}{h}$
- The forward finite difference: $du/dt \approx (D^+u)_j=\frac{u_{j+1}-u_j}{h}$
- The central finite difference: $du/dt \approx (D^ \pm u)_j =\frac{u_{j+1}-u_{j-1}}{2h}$ 
- The second central finite difference: $d^2u/dt^2 \approx (D^2u)_j=\frac{u_{j+1}-2u_j+u_{j-1}}{h^2}$ 


### Discretization 

The [Laplace Operator](Laplace%20Operator.md) says $\nabla^2 f  = \frac{\partial ^2 f}{\partial x^2}+\frac{\partial^2f}{\partial y^2}$ . Using the second central finite difference (shown above in [Numeric Derivatives](Poisson's%20equation.md#Numeric%20Derivatives)) allows us to approximate this as:

$$\nabla^2 f \approx \frac{f_{i+1,j}-2f_{i,j}+f_{i-1,j}}{\Delta x^2}+\frac{f_{i,j+1}-2f_{i,j}+f_{i,j-1}}{\Delta y^2}$$

So, if $\nabla ^2 f = \sigma(x)$, we can write this as:


$$0= \frac{f_{i+1,j}-2f_{i,j}+f_{i-1,j}}{\Delta x^2}+\frac{f_{i,j+1}-2f_{i,j}+f_{i,j-1}}{\Delta y^2}+\sigma$$

If $\Delta x = \Delta y$, we can write this as:

$$(\nabla^2f)_{ij}=\frac{1}{\Delta x^2}\left( f_{i_1,j}+f_{i-1,j}+f_{i, j+1}+f_{i,j-1}-4f_{ij} \right)=\sigma_{ij}$$

or

$$(\nabla^2f)_{ij}=4f_{ij}-f_{i_1,j}-f_{i-1,j}-f_{i, j+1}-f_{i,j-1}=\Delta x^2(\sigma_{ij})$$

If $f$ is discretized to an $M\times N$ grid, this equation will hold for $i=2, \dots, N-1$ and $j=2, \dots, M-1$[^4]

### Solving

To solve this, we unwrap $f$ into a vector:

$$\vec f = [f_{11}, f_{21}, \dots, f_{M1}, f_{12}, f_{22}, \dots,f_{m2},\dots, f_{mn}]^T$$


Along with $\sigma$:

$$\vec \sigma = -\Delta x^2[\sigma_{11}, \sigma_{21}, \dots]^T \qquad \text{(Same pattern as \textbf f)}$$



This results in an $MN \times MN$ system of:

$$\textbf A \vec f = \vec \sigma$$

where:

$$A = \begin{bmatrix}

D & -I&0&0&0&\cdots&0\\
-I&D&-I&0&0&\cdots&0\\
0&-I&D&-I&0&\cdots&0\\
\vdots&\ddots&\ddots&\ddots&\ddots&\ddots&\vdots\\
0&\cdots&0&-I&D&-I&0\\
0&\cdots&\cdots&0&-I&D&-I\\
0 &\cdots&\cdots&\cdots&0&-I&D

\end{bmatrix}
$$

where $I$ is the $M \times M$ identity matrix and $D$ is an $M \times M$ matrix defined as:

$$D=\begin{bmatrix}

4 & -1&0&0&0&\cdots&0\\
-1&4&-1&0&0&\cdots&0\\
0&-1&4&-1&0&\cdots&0\\
\vdots&\ddots&\ddots&\ddots&\ddots&\ddots&\vdots\\
0&\cdots&0&-1&4&-1&0\\
0&\cdots&\cdots&0&-1&4&-1\\
0 &\cdots&\cdots&\cdots&0&-1&4
\end{bmatrix}$$


For instance, if $M=3$ and $N=3$, giving a $3\times3$ grid, $A$ would be:

$$
A = \begin{bmatrix}
 4 & -1 &  0 & \big| & -1 &  0 &  0 & \big| &  0 &  0 &  0 \\
-1 &  4 & -1 & \big| &  0 & -1 &  0 & \big| &  0 &  0 &  0 \\
 0 & -1 &  4 & \big| &  0 &  0 & -1 & \big| &  0 &  0 &  0 \\
\hline
-1 &  0 &  0 & \big| &  4 & -1 &  0 & \big| & -1 &  0 &  0 \\
 0 & -1 &  0 & \big| & -1 &  4 & -1 & \big| &  0 & -1 &  0 \\
 0 &  0 & -1 & \big| &  0 & -1 &  4 & \big| &  0 &  0 & -1 \\
\hline
 0 &  0 &  0 & \big| & -1 &  0 &  0 & \big| &  4 & -1 &  0 \\
 0 &  0 &  0 & \big| &  0 & -1 &  0 & \big| & -1 &  4 & -1 \\
 0 &  0 &  0 & \big| &  0 &  0 & -1 & \big| &  0 & -1 &  4
\end{bmatrix}
$$

### Boundary Conditions

#### Dirichlet

From Wikipedia:

> It is important to note that prescribed values of $u$ (usually laying on the boundary) would have their corresponding elements removed from $I$ and $D$.

This means we need to eliminate boundary values from the system. For *Dirichlet* boundary conditions, where $f$ is known at the boundaries, we can simply modify the vector $\vec \sigma$. *Without boundary conditions,* the $\sigma$ that corresponds to $A$ above would be:

$$
\sigma = \begin{bmatrix}
-\Delta x^2 f_{22}\\
-\Delta x^2 f_{32}\\
-\Delta x^2 f_{42}\\
-\Delta x^2 f_{23}\\
-\Delta x^2 f_{33}\\
-\Delta x^2 f_{43}\\
-\Delta x^2 f_{24}\\
-\Delta x^2 f_{34}\\
-\Delta x^2 f_{44}\\
\end{bmatrix}
$$

But, after imposing boundary conditions, it might look something like.

$$
\sigma = \left[
\begin{array}{l}
-\Delta x^2 f_{22} + u_{12} + u_{21} \\
-\Delta x^2 f_{32} + u_{31} \\
-\Delta x^2 f_{42} + u_{52} + u_{41} \\
-\Delta x^2 f_{23} + u_{13} \\
-\Delta x^2 f_{33} \\
-\Delta x^2 f_{43} + u_{53} \\
-\Delta x^2 f_{24} + u_{14} + u_{25} \\
-\Delta x^2 f_{34} + u_{35} \\
-\Delta x^2 f_{44} + u_{54} + u_{45}
\end{array}
\right]
$$

#### Neumann 

Neuman conditions enforce:

$$\frac{\partial f}{\partial x}|_b=g_0$$

In english, we know the derivative of the function at the boundary .

*In 1D*, if the boundary occurs at $i=1$, we can define a **ghost point** at $i=0$, and use this point to assert the condition.

$$\frac{f_2-\overbrace{f_0}^{\text{Ghost point}}}{2 \Delta x} = g_0 \qquad \Rightarrow \quad f_0=f_2-2\Delta xg_0 $$

Then, we would substitute this into the Laplacian stencil at the boundaries. 

*In 2D,* a ghost point at $j=0$ would be:


$$\frac{f_{i,2}-f_{i,0}}{2 \Delta y}=g_{i,1}$$

which again reduces to:

$$f_{i,0}=f_{i,2}-2\Delta y g_{i,1}$$

Now, the laplacian *at the boundary point* is:

$$(\nabla^2 f)_{i1}= \frac{f_{i+1,1}-2f_{i,1}+f_{i-1,1}}{\Delta x^2}+\frac{f_{i,2}-2f_{i,1}+f_{i,0}}{\Delta y^2}$$

> This is unchanged from before. However, in the actual computation, there would be no definition for $f_{i,0}$ and it would be ignored. Now we have a definition.

Substituting the expression for $f_{i,0}$ yields:

$$(\nabla ^2 f)_{i1}=\frac{f_{i+1,1}-2f_{i,1}+f_{i-1,1}}{\Delta x^2}+\frac{f_{i,2}+(f_{i,2}-2\Delta y g_{i,1})-2 f_{i,1}}{\Delta y^2}$$

Notice that if $g_{i, 1}=0$, this reduces to:

$$(\nabla ^2 f)_{i1}=\frac{f_{i+1,1}-2f_{i,1}+f_{i-1,1}}{\Delta x^2}+\frac{2f_{i,2}-2 f_{i,1}}{\Delta y^2}$$










## References

- https://www.math.uci.edu/~chenlong/226/FDM.pdf



[^1]: https://en.wikipedia.org/wiki/Dirichlet_boundary_condition
[^2]: https://en.wikipedia.org/wiki/Neumann_boundary_condition

[^3]: https://en.wikipedia.org/wiki/Laplace_operator

[^4]: https://en.wikipedia.org/wiki/Discrete_Poisson_equation
