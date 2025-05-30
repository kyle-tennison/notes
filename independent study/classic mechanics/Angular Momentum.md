# Angular Momentum

$$
\begin{aligned}
\frac{d}{dt}\Bigl(\sum_i \frac{\partial L}{\partial \dot q_i}\Bigr)
&= \sum_i \frac{d}{dt}\Bigl(\frac{\partial L}{\partial \dot q_i}\Bigr) \\[6pt]
&= \sum_i \Biggl[\,
      \sum_j \frac{\partial^2 L}{\partial q_j\,\partial \dot q_i}\,\dot q_j
    + \sum_j \frac{\partial^2 L}{\partial \dot q_j\,\partial \dot q_i}\,\ddot q_j
    + \frac{\partial^2 L}{\partial t\,\partial \dot q_i}
  \Biggr] \\[6pt]
&= \sum_{i,j}\frac{\partial^2 L}{\partial q_j\,\partial \dot q_i}\,\dot q_j
  \;+\;\sum_{i,j}\frac{\partial^2 L}{\partial \dot q_j\,\partial \dot q_i}\,\ddot q_j
  \;+\;\sum_i\frac{\partial^2 L}{\partial t\,\partial \dot q_i}
\end{aligned}
$$

If the Euler–Lagrange equations hold,
$$
\frac{d}{dt}\bigl(\tfrac{\partial L}{\partial \dot q_i}\bigr)
= \frac{\partial L}{\partial q_i},
$$
then on‐shell one finds
$$
\begin{aligned}
\frac{d}{dt}\Bigl(\sum_i \frac{\partial L}{\partial \dot q_i}\Bigr)
&= \sum_i \frac{\partial L}{\partial q_i}\,.
\end{aligned}
$$