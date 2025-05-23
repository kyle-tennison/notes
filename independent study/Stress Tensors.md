# Stress Tensors

The stress tensor represents the state of stress for a (usually) infinitesimal material element. Each face of the element has one normal stress and two shear stresses.

![[image-25.png]]

The typical subscript notation is $\sigma_{ab}$, where $a$ is the axis of the face and $b$ is the direction that the stress points. You can collect all of these stresses and put them into a matrix:

$$\textbf{T} \equiv \begin{bmatrix}
\sigma_{xx} & \sigma_{xy} & \sigma_{xz} \\
\sigma_{yx} & \sigma_{yy} & \sigma_{yz} \\
\sigma_{zx} & \sigma_{zy} & \sigma_{zz} \\
\end{bmatrix}$$

Where $\textbf{T}$ is the **Stress Tensor**. 

If you want to then find the *stress in any direction*, you can use:

$$\vec \sigma_n=\hat n\cdot \textbf{T}$$

where $\vec \sigma_n$ is the stress in the $\hat n$ direction.

## Net Forces


The *net force* on a body can be described as:

$$\vec F=\iint_S\vec \sigma_n dS = \iint_S\hat n \cdot \textbf{T}\;dS$$

i.e., integrating over all surface stress (force/area) to get net force. Then, by the [Divergence Theorem](Divergence%20Theorem.md), this can be expressed as:

$$\vec F = \iiint_{V}\nabla \cdot \textbf{T}\;dV$$

Because T is a tensor, the divergence will be a vector:

$$\nabla \cdot \boldsymbol{T} =
\begin{bmatrix}
\frac{\partial \sigma_{xx}}{\partial x} + \frac{\partial \sigma_{xy}}{\partial y} + \frac{\partial \sigma_{xz}}{\partial z} \\
\frac{\partial \sigma_{yx}}{\partial x} + \frac{\partial \sigma_{yy}}{\partial y} + \frac{\partial \sigma_{yz}}{\partial z} \\
\frac{\partial \sigma_{zx}}{\partial x} + \frac{\partial \sigma_{zy}}{\partial y} + \frac{\partial \sigma_{zz}}{\partial z}
\end{bmatrix}$$


Physically, this divergence is really just the *net force per unit volume*.


## References

```vid
https://www.youtube.com/watch?v=uO_bW2zzrNU
Title: The stress tensor
Author: Brian Storey
Thumbnail: https://i.ytimg.com/vi/uO_bW2zzrNU/mqdefault.jpg
AuthorUrl: https://www.youtube.com/@brianstorey7830
```