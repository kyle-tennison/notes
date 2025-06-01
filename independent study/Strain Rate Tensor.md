# Strain Rate Tensor



The Taylor Series expansion of velocity at some removed point is:

$$\textbf v(\textbf p + r, t) \approx \textbf v(\textbf p, t)+(\nabla \textbf v)(\textbf p, t)(\textbf r)+\cdots$$

Neglecting higher order terms.

Notice that $(\nabla \textbf v)^T$ is related to the Jacobian matrix  of the field:

$$(\nabla \textbf v)^T=\begin{bmatrix}

\frac{\partial v_x}{\partial x} & \frac{\partial v_x}{\partial y} & \frac{\partial v_x}{\partial z} \\

\frac{\partial v_y}{\partial x} & \frac{\partial v_y}{\partial y} & \frac{\partial v_y}{\partial z} \\

\frac{\partial v_z}{\partial x} & \frac{\partial v_z}{\partial y} & \frac{\partial v_z}{\partial z} \\

\end{bmatrix} = \textbf J$$

We can rewrite the Taylor series approximation as:

$$\textbf v(\textbf p +r, t) \approx \textbf v(\textbf p, t) +\textbf J(\textbf p, t)\textbf r$$

We can then decompose the $\textbf J(\textbf p, t)$ term into a symmetric matrix $\textbf E$ and an asymmetric matrix $\textbf R$, giving:

$$\textbf v(\textbf p+\textbf r, t) \approx \textbf v(\textbf p,t)+\textbf E(\textbf p, t)(\textbf r)+\textbf R(\textbf p, t)(\textbf r)$$

where $\textbf E = \frac12 (\textbf J + \textbf J^T)$  and $\textbf R = \frac12 (\textbf J - \textbf J^T)$ . 

In the context of a fluid, $\textbf E$ gives the "strain rate" (i.e. the rate of deformation) of the flow, whereas $\textbf R$ gives the rotation of the flow. 


### Connection with the Strain Tensor

The strain rate is the time derivative of the *strain tensor*, which is:

$$
\underline{\underline{\epsilon}} =
\begin{bmatrix}
\epsilon_{xx} & \epsilon_{xy} & \epsilon_{xz} \\
\epsilon_{yx} & \epsilon_{yy} & \epsilon_{yz} \\
\epsilon_{zx} & \epsilon_{zy} & \epsilon_{zz}
\end{bmatrix}
=
\begin{bmatrix}
\epsilon_{xx} & \frac{1}{2}\gamma_{xy} & \frac{1}{2}\gamma_{xz} \\
\frac{1}{2}\gamma_{yx} & \epsilon_{yy} & \frac{1}{2}\gamma_{yz} \\
\frac{1}{2}\gamma_{zx} & \frac{1}{2}\gamma_{zy} & \epsilon_{zz}
\end{bmatrix}
$$

Strain, in 1D is usually expressed as $\epsilon = ∆L/L$, which is the same as saying $\epsilon_x = \partial u / \partial x$ *where u is the displacement field (not velocity)*. In two dimensions, there are two potential expressions:

For *normal* strains, the strain is still $\epsilon _{xx}=  \frac{\partial u_x}{\partial x}$, $\epsilon _{yy}=  \frac{\partial u_y}{\partial x}$, etc. However, shear strains are in the form of $\epsilon_{xy} = \frac{1}{2}(\frac{\partial u_x}{\partial y} + \frac{\partial u_y}{\partial x})$ . You can combine these into the following expression for strain:

$$\epsilon _{ij} = \frac12 (\frac{\partial u_i}{\partial x_j}+\frac{\partial u_j}{\partial x_i})$$

When $i = j$, the two terms are equal and everything simplifies into a single term. 

Now, taking the time derivative of this gives:

$$\dot \epsilon _{ij} = \frac12 (\frac{\partial v_i}{\partial x_j}+\frac{\partial v_j}{\partial x_i})$$
This can be re-written in vector form as:

$$\boldsymbol {\dot \epsilon } =  \frac{1}{2}\left(\nabla \textbf v + (\nabla \textbf v)^T \right)$$

Above, we saw that $(\nabla \textbf v)^T = \textbf J$, which means this can also be written as:

$$\boldsymbol {\dot \epsilon } = \frac{1}{2}\left(\textbf J^T + \textbf J \right)$$

Which shows that $\textbf E = \frac12 (\textbf J + \textbf J^T)$ is indeed the strain rate.

