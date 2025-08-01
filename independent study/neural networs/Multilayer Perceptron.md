# Multilayer Perceptron


A **neuron**, in the context of neural networks, is simply a node that can hold a value between 0 and 1. The number that a neuron holds is called the *activation*.

The input to the network is an array of neurons, and the output is also an array of neurons. The activation of the output neurons can be decoded to mean something useful.

Each **layer** is determined by the activations of the previous layer. Layers can vary in size, and there can be any number of layers. The layers that sit between the input and output layers are called the **hidden layers**.

For each node in the hidden and output layers, there is a connection to *every node in the previous layer*. For instance, a single node in layer 2 will have connections to every node in layer 1. Then, if we assign **weights** to these connections, we can make the activation of this node in layer 2 a **weighted sum** of all of the layer 1 nodes' activations, *times* the assigned weight.

We can say the activation for the 0th node in layer 1, $a_0^{(1)}$, can be expressed as:

$$a_0^{(1)}=\sigma(w_{0,0}a_0^{(0)}+w_{0,1}a_1^{(0)}+\dots+w_{0,n}a_n^{(0)}+b_0)$$

where:
- $a_n^{(m)}$ is the $n^{th}$ node in the $m^{th}$ layer
- $b_n$ is the bias for the $n^{th}$ node (see note)

> Would $b_n$ change with the layers? I would imagine so?

We can alternatively express this as a matrix product:

$$
\textbf{a}^{(1)} =
\sigma \begin{pmatrix} 

\begin{bmatrix}
w_{0,0} & w_{0,1} & \cdots & w_{0,n} \\
w_{1,0} & w_{1,1} & \cdots & w_{1,n} \\
\vdots & \vdots & \ddots & \vdots \\
w_{m,0} & w_{m,1} & \cdots & w_{m,n} \\
\end{bmatrix}

\begin{bmatrix}
a_0^{(0)} \\
a_1^{(0)} \\
\vdots \\
a_n^{(0)} \\
\end{bmatrix}

+

\begin{bmatrix}
b_0 \\
b_1 \\
\vdots \\
b_n
\end{bmatrix}
\end{pmatrix} 
$$

> 🤖 (notecheck comment) - The dimensions for the weight matrix and bias vector are inconsistent. In the above matrix product, the weight matrix is arranged to produce output neurons indexed from 0 to m (i.e. m+1 neurons), so the bias vector should have m+1 entries (b₀, …, bₘ) rather than being indexed up to n.

> You would apply the Sigmoid function for each row of the resulting vector.

Equivalently, you can say:

$$\textbf{a}^{(1)}=\sigma \big(\textbf{W} \textbf{a}^{(0)}+\textbf{b}  \big)$$

$$$$

When you do this weighted average, you can get any output, but because the activation should be between 0 and 1, we need to scale the number into this range. Often, a logistic function called the *Sigmoid* is used for this:

$$\sigma(x)=\frac{1}{1+e^{-x}}$$

![[Pasted image 20250205131042.png]]

You can also add some **bias** to the weighted sum. You add this bias to the weighted sum before adding it to the Sigmoid function. 

So each node has weights and biases tied to every node in the previous layer, which means there are an incredibly high number of parameters that can be tuned in the network. When we say that a network is "**learning**," we are iteratively tuning these weights and biases until we get a network that produces a desired result.

### References

```vid
https://www.youtube.com/watch?v=aircAruvnKk&list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi
Title: But what is a neural network? | Deep learning chapter 1
Author: 3Blue1Brown
Thumbnail: https://i.ytimg.com/vi/aircAruvnKk/mqdefault.jpg
AuthorUrl: https://www.youtube.com/@3blue1brown
```