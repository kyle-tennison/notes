# Gradient Descent

To start, assign all the weights randomly. Then, pass a sample to the network and compare the real output to the expected output. Next, square the differences between the two vectors, and then take the sum of the resulting values; this is the **cost** of the network, which roughly represents how poorly it performs. If the cost is near zero, then the network performs well.

If you perform this for many samples in a dataset and take the average cost over each training sample, you can get an estimate of the network's overall performance.

So now, you have some *function* whose parameters are all the weights and biases, and which returns a scalar that represents the performance of the network. We want to find the **minimum** of this function.

For a single-variable function, if you move in the direction that the slope "points" (whichever direction is negative), you'll eventually find a local minimum. If your step size is proportional to the slope, as you approach the minimum, you'll take smaller and smaller steps and reach a more precise solution.

This approach doesn't guarantee a global minimum—only a local minimum. Depending on where this iteration begins, you may get different minima.

If you're working with a multivariable function, you can use the gradient to find the direction of quickest increase; going in the opposite direction will give the quickest decrease.

If you assemble all weights and biases into a $1 \times n$ vector called $\textbf{W}$, then one iteration of gradient descent will look like:

$$\textbf W_{i+1}=-\nabla C(\textbf W)$$
> 🤖 (notecheck comment) - This formula is missing the previous iteration's weights and the learning rate factor. A more complete version is:  
>   $\textbf{W}_{i+1} = \textbf{W}_i - \alpha \nabla C(\textbf{W}_i)$,  
> where $\alpha$ is the learning rate.

where $C$ is the cost.

### References

```vid
https://www.youtube.com/watch?v=IHZwWFHWa-w&list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi&index=2
Title: Gradient descent, how neural networks learn | DL2
Author: 3Blue1Brown
Thumbnail: https://i.ytimg.com/vi/IHZwWFHWa-w/mqdefault.jpg
AuthorUrl: https://www.youtube.com/@3blue1brown
```