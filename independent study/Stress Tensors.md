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

i.e., integrating over all surface stress (force/area) to get the net force. Then, by the [Divergence Theorem](Divergence%20Theorem.md), this can be expressed as:

$$\vec F = \iiint_{V}\nabla \cdot \textbf{T}\;dV$$

Because T is a tensor, the divergence will be a vector:

$$\nabla \cdot \boldsymbol{T} =
\begin{bmatrix}
\frac{\partial \sigma_{xx}}{\partial x} + \frac{\partial \sigma_{xy}}{\partial y} + \frac{\partial \sigma_{xz}}{\partial z} \\
\frac{\partial \sigma_{yx}}{\partial x} + \frac{\partial \sigma_{yy}}{\partial y} + \frac{\partial \sigma_{yz}}{\partial z} \\
\frac{\partial \sigma_{zx}}{\partial x} + \frac{\partial \sigma_{zy}}{\partial y} + \frac{\partial \sigma_{zz}}{\partial z}
\end{bmatrix}$$

Physically, this divergence is really just the *net force per unit volume*.
^divergence-of-stress-tensor

### Directional Forces

![[image-26.png]]

If you are trying to find the net force along the x-axis (shown here), you need to account for how the force will change over the material element. For example, the green value at the bottom shows:

$$-\sigma_{yx}dxdz$$

This is the shear stress (force/area) times the area of the $dx\cdot dz$ face on the material element, given a partition of force in the x direction. Then, at the top is its complementary stress (also in green), shown as:

$$\left( \sigma_{yx}+\frac{\partial \sigma_{yx}}{\partial y}dy \right)dxdz$$

Here, we need to add $\left(\frac{\partial \sigma_{yx}}{\partial y}\right)dy$ to account for the *change in stress over the element's size*. This is simply a first-order expansion of the Taylor series.

## Stress Deviator Tensor

^e76ff6

A stress tensor can be expressed as the sum of two other stress tensors:

1. A [*hydrostatic stress*](https://en.wikipedia.org/wiki/Hydrostatic_stress) tensor $\pi \delta_{ij}$ (i.e., just a tensor with 3 normal stresses). This tends to change the volume of the body.
2. A *deviatoric component* $\boldsymbol \tau$ called the **stress deviator tensor**. This tends to deform the body.

The stress tensor is simply the sum of these two partitions:

$\sigma_{ij}=s_{ij}+\pi \delta_{ij}$ 

where $\pi$ is the mean stress, given by:

$$\pi = \frac{\sigma_{xx}+\sigma_{yy}+\sigma_{zz}}{3}$$

and $\delta_{ij}$ is the Kronecker delta (i.e. just the components of an identity matrix; $(\textbf I)_{ij} = \delta_{ij}$). 


This is also *one-third the trace (diagonal sum) of the stress tensor*. In $\mathbb{R}^3$, this works out to:

$$\begin{aligned}
\begin{bmatrix}
s_{xx} & s_{xy} & s_{xz} \\
s_{yx} & s_{yy} & s_{yz} \\
s_{zx} & s_{zy} & s_{zz}
\end{bmatrix}
&=
\begin{bmatrix}
\sigma_{xx} & \sigma_{xy} & \sigma_{xz} \\
\sigma_{yx} & \sigma_{yy} & \sigma_{yz} \\
\sigma_{zx} & \sigma_{zy} & \sigma_{zz}
\end{bmatrix}
-
\begin{bmatrix}
\pi & 0 & 0 \\
0 & \pi & 0 \\
0 & 0 & \pi
\end{bmatrix} \\
&=
\begin{bmatrix}
\sigma_{xx} - \pi & \sigma_{xy} & \sigma_{xz} \\
\sigma_{yx} & \sigma_{yy} - \pi & \sigma_{yz} \\
\sigma_{zx} & \sigma_{zy} & \sigma_{zz} - \pi
\end{bmatrix}.
\end{aligned}$$



### Definition by Strain Rate 

In fluids, the stress deviator tensor can be written in terms of the [Strain Rate Tensor](Strain%20Rate%20Tensor.md) (for reasons that are beyond my understanding). The idea is that two physical constants $A$ and $B$ exist that allow:

$$\tau _{ij}= Ae_{ij}+B e_{kk}\delta{ij}$$

where $e_{kk}$ is simply the trace of $\textbf e$. In vector form, this is:

$$\boldsymbol \tau = A \textbf e + B (\;\textbf{tr(e)\;})\textbf I$$

Physically, it is found that $A = 2 \mu$ and $B = \lambda$ , where $\mu$ is shear viscosity and $\lambda$ is bulk viscosity.



## References

```vid
https://www.youtube.com/watch?v=uO_bW2zzrNU
Title: The stress tensor
Author: Brian Storey
Thumbnail: https://i.ytimg.com/vi/uO_bW2zzrNU/mqdefault.jpg
AuthorUrl: https://www.youtube.com/@brianstorey7830
```