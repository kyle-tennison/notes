# Back Propagation


## Back Propagation of a single-node-layered NN

![[image-32.png]]


Here, $C$ is a cost function, which depends on the weights and biases between each of these nodes. We need to find a way to modify these weights and biases systematically such that they $\min C$ . 

Some notation:

- $a^{(L)}$ refers to the *activation* of the node in layer $L$—i.e. the last layer. The node in the layer before last, $L-1$, would have its action denoted as $a^{L-1}$
  

- The relationship between layers is given as:
  $$a^{(L)}=\sigma ( w^{(L)}a^{(L-1)}+b^{(L)}) \tag 1$$
  
  where $w^{(L)}$ and  $b^{(L)}$ are the weight and bias (respectively) of the node in layer $L-1$ to the node in layer $L$. $\sigma$ is the sigmoid function.


- Sometimes the notation below is used to summarize: $$z^{(L)}=w^{(L)}a^{(L-1)}+b^{(L)} \tag 2$$
- $y$ refers to the desired output of the output neuron, such that the cost function is defined as $C = (a^{(L)}-y)^2$ 
  
- $C_i$ refers to the cost of the $i^{th}$ training example

---

For each weight (but focusing on layer $L$ for now), we want to know:

$$\frac{\partial C_0}{\partial w^{(L)}}$$
which will tell us how to update the weight. To get here, you just apply the chain rule:

$$\frac{\partial C_0}{\partial w^{(L)}}=\frac{\partial z^{(L)}}{\partial w^{(L)}}\frac{\partial a^{(L)}}{\partial z^{(L)}}\frac{\partial C_0}{\partial a^{(L)}} \tag 3$$

To begin evaluating this, the derivative $\partial C_0 / \partial a^{(L)}$ can be found by deriving $C_0 = (a^{(L)}-y)^2$ (mentioned above), which yields:

$$\frac{\partial C_0}{\partial a^{(L)}}=2(a^{(L)}-y) \tag 4$$

Then, because $a^{(L)}=\sigma (z^{(L)})$ the derivative $\partial a^{(L)} / \partial z ^{(L)}$ is simply:

$$\frac{\partial a^{(L)}}{\partial z^{(L)}} = \sigma '(z^{(L)}) \tag 5$$

And, finally, from Eq. 2 we can say:

$$ \frac{\partial z^{(L)}}{\partial w^{(L)}} = a^{(L-1)}  \tag 6$$

---

The same can be done for the partial of the bias:

$$\frac{\partial C_0}{\partial b^{(L)}}=\frac{\partial z^{(L)}}{\partial b^{(L)}}\frac{\partial a^{(L)}}{\partial z^{(L)}}\frac{\partial C_0}{\partial a^{(L)}} \tag 7$$


where $\partial z^{(L)} / \partial b^{(L)} = 1$ . 

--- 

Similarly, if we want to see how the previous layer's activation *should* change (though we can't directly change it—we can only change weights & biases) we can compute:

$$\frac{\partial C_0}{\partial a^{(L-1)}}=\frac{\partial z^{(L)}}{\partial a^{(L-1)}}\frac{\partial a^{(L)}}{\partial z^{(L)}}\frac{\partial C_0}{\partial a^{(L)}} \tag 8$$

Where $\partial z^{(L)} / \partial a^{(L-1)} = w^{(L)}$ 

Now that ${\partial C_0}/{\partial a^{(L-1)}}$ is known, you can keep iterating this idea for each layer. This quantity replaces the need for Eq. 4 in previous layers.

## Multi-node Backpropagation 


 $a^{(L)}_i$ now refers to the activation of the $i^{th}$ node in the $L$ layer. The same is true for other subscripts (with exception to the cost function, where the subscript continues to identify the training example index).

Now, the cost function is given as:

$$C_0 = \sum_{j=0}^{n_L-1}(a_j^{(L)}-y_j)^2$$

where $j$ represents the neuron index in layer $L$ and $k$ (not shown) represents the neuron index in layer $L-1$. 

The notation of weights is now: $w^{(L)}_{jk}$ to represent the weight between neuron $k$ in layer $L-1$ to neuron $j$ in layer $L$. 

Now, the function $z_j^{(L)}$ is represented as:

$$z_j^{(L)} = \left [\sum_{i=0}w_{ji}^{(L)} a_i^{(L-1)} \right ] + b_j^{(L)}$$


![[image-33.png|352x219]]

For instance, given the network above, this would look like

$$z_j^{(L)} = w_{j0}^{(L)}a_0^{(L-1)} + w_{j1}^{(L)}a_1^{(L-1)} + w_{j2}^{(L)}a_2^{(L-1)} + b_j^{(L)}$$



Other changes are:

- $$a_j^{(L)} = \sigma (z_j^{(L)})$$
- $$\frac{\partial C_0}{\partial w_{jk}^{(L)}} = \frac{\partial z_j^{(L)}}{\partial w_{jk}^{(L)}} \frac{\partial a_j^{(L)}}{\partial z_j^{(L)}} \frac{\partial C_0}{\partial a_j^{(L)}}$$
The primary difference is that the partial wrt action is now the sum over layer L

$$\frac{\partial C_0}{\partial a_k^{(L-1)}} = \sum_{j=0}^{n_L-1} \frac{\partial z_j^{(L)}}{\partial a_k^{(L-1)}} \frac{\partial a_j^{(L)}}{\partial z_j^{(L)}} \frac{\partial C_0}{\partial a_j^{(L)}}$$







### References

```vid
https://www.youtube.com/watch?v=tIeHLnjs5U8
Title: Backpropagation calculus | Deep Learning Chapter 4
Author: 3Blue1Brown
Thumbnail: https://i.ytimg.com/vi/tIeHLnjs5U8/mqdefault.jpg
AuthorUrl: https://www.youtube.com/@3blue1brown
```