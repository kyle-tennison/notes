# Frame Rotations

This is a pain point for me, so I'm dedicating a page to it.

![](excalidraw-2025-11-27-10.45.29.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2025-11-27-10.45.29.excalidraw.md)%%


Consider this example. The frame $B$ is a counter-clockwise shift from the $I$ frame. 

We can see from trigonometry that:

$$\mathbf v = v \hat {\bf I} = -v \cos(\theta) \hat{\bf I_B}+ v \sin(\theta)\hat{\bf J_B}$$

If we want to *rotate a vector* counter-clockwise by $\theta$, we use the equation:

$$\mathbf v' = \mathbf R \mathbf v$$

where 

$$
\mathbf R =\begin{bmatrix}
\cos(\theta) & - \sin(\theta)\\ 
\sin(\theta) & \cos(\theta)
\end{bmatrix}$$

If we are instead doing a *clockwise* shift, we use $\mathbf v' = \mathbf R^{\rm T} \mathbf v$ which is:

$$\mathbf R^{\rm T} =\begin{bmatrix}
\cos(\theta) & \sin(\theta)\\ 
-\sin(\theta) & \cos(\theta)
\end{bmatrix}$$

Now, in this above example, **we are rotating the frame, not the vector**. In cases like this, were we are performing a counter-clockwise *frame rotation* of $\theta$, we may re-express $\mathbf v$ in a new frame as:

$$\mathbf v_{B} = \mathbf R \mathbf v_{I}$$

The difference here is that:

$$\mathbf v' \ne \mathbf v$$

but

$$\mathbf v_B = \mathbf v_I \quad \text{just in different coord systems}$$



So, applying this to $\mathbf v$ in the example shows:

$$\mathbf v_B = \mathbf R^{\rm T}\mathbf v_I = 
\begin{bmatrix}
\cos (\theta) & \sin(\theta)\\
- \sin(\theta) & \cos(\theta)
\end{bmatrix}
\binom{v}{0} = \binom{v \cos(\theta)}{-v \sin(\theta)}
$$

which agrees with what we found trigonometrically. 