# Uncertainty

## Interpreting Bounds

With uncertainty bounds, you can either:
1. Contain a metric between the bounds
2. Exceed the metric by both bounds
3. Fall short of the metric at both bounds

![](excalidraw-2026-09-15-20.08.01.excalidraw.svg)
%%[🖋 Edit in Excalidraw](excalidraw-2026-09-15-20.08.01.excalidraw.md)%%



Say you are trying to prove that something meets a force criterion. For *Case 1* your uncertainty interval of X% allows you to conclude:
> We cannot conclude with X% confidence that the criterion is met.

If you definitely exceed the metric as in *Case 2*, you can say:
> We can conclude with X% confidence that the criterion is met.

And in *Case 3* where you definitely fall short, you can say:
> We can conclude with X% confidence that the criterion is not met.


## Calculating Bounds

The [Central Limit Theorem](3.%20General%20Random%20Variables.md#Central%20Limit%20Theorem) says that (effectively) the sum/average many samples of random distribution will eventually tend towards a gaussian distribution. Hence, in this class we mostly treat our error as gaussian.

Gaussian distributions [(discussed here)](3.%20General%20Random%20Variables.md#Normal%20Random%20Variables) have the following key properties:
- Expected Value: $\mu$ 
- Standard Deviation: $\sigma = \sqrt v$

![](https://www.researchgate.net/publication/317132340/figure/fig3/AS:498152629587972@1495780250875/The-normal-distribution-and-standard-deviation-with-the-confidence-level.png)

As shown in the figure above, common confidence intervals can be calculated simply by adding a multiple of the standard deviation $\sigma$ to the mean $\mu$.

$$[\mu - \sigma, \mu + \sigma] \qquad \text{(68.3\% Confidence)}$$
$$[\mu - 2\sigma, \mu + 2\sigma] \qquad \text{(95.4\% Confidence)}$$
$$[\mu - 3\sigma, \mu + 3\sigma] \qquad \text{(99.7\% Confidence)}$$

### Standard Error

With one sample, there is a 68.3% chance of it being $\in \mu \pm \sigma$. 

However, as you take more samples and *average* them together, their mean is more likely to be in $\mu \pm \sigma$. We can characterize this with **standard error**, which says:

$$\sigma_{\bar x} = \frac{\sigma}{\sqrt n}$$

We see that as $n \to \infty, \sigma_{\bar x} \to 0$.

> This is sometimes called the standard error of the mean.

If you take multiple samples with this method, you can reduce the size of your confidence interval without decreasing the confidence:


$$[\mu - \frac{\sigma}{\sqrt n}, \mu + \frac{\sigma}{\sqrt n}] \qquad \text{(68.3\% Confidence)}$$
$$[\mu - 2\frac{\sigma}{\sqrt n}, \mu + 2\frac{\sigma}{\sqrt n}] \qquad \text{(95.4\% Confidence)}$$
$$[\mu - 3\frac{\sigma}{\sqrt n}, \mu + 3\frac{\sigma}{\sqrt n}] \qquad \text{(99.7\% Confidence)}$$

## Samples vs Population Standard Deviation

The population standard deviation $\sigma$ is:

$$\sigma = \sqrt{\frac{1}{N}\sum_{i=1}^{N}(x_i - \mu)^2}$$

While the sample standard deviation is:

$$s = \sqrt{\frac{1}{n-1}\sum_{i=1}^{n}(x_i - \bar{x})^2}$$

Where $\bar x$ is the sample mean,

$$\bar x = x \frac{\sum^n_{i=1} x_i}{n}$$

which differs from the population standard deviation, which is:

$$\mu = \frac{\sum^n_{i=1} x_i}{N}$$

where $N$ is the total number of specimen in the population, and $n$ is the number of samples. 

Then, like [Standard Error](#Standard%20Error), we can instead calculate the *Sample Standard Deviation of the Mean*:

$$s_{\bar x} = \frac{s}{\sqrt n}$$


## Combined Uncertainty

$n$ independent uncertainties may be combined as follows to create a combined/total uncertainty:

$$U_\text{tot.} = \sqrt{U_1^2+U_2^2+\cdots+U_n^2}$$

## Rectangular Distribution

From: https://physics.stackexchange.com/questions/110242/why-is-uncertainty-divided-by-sqrt3

![[image-147.png]]

If you have some tolerance, like the smallest unit on a ruler, you can assume a rectangular distribuiton of the "actual" value being in some $[a,b]$.

For instance, something with a tolerance $\pm \rm 1\ mm$ would have:

$$a = \text{measurement} - 1 {\rm \ mm}$$
$$b = \text{measurement} + 1 {\rm \ mm}$$
Notice that $\text{tol} = \frac 12 (b-a)$. 

For such a distribution, the expected value is (from [Expectation, Variance](3.%20General%20Random%20Variables.md#Expectation,%20Variance)):

$$E(X)
= \int_a^b xp(x)\mathrm{d}x
= \int_a^b \frac{x}{b - a}\mathrm{d}x
= \left.\frac{1}{2}\frac{x^2}{b - a}\right|_a^b = \frac{1}{2}\frac{b^2 - a^2}{b - a} = \frac{b + a}{2}$$
The standard deviation is then found from:
$$
\begin{align}
\sigma^2
&= \int_a^b \bigl(x - E(x)\bigr)^2 p(x)\mathrm{d}x \\
&= \int_a^b \biggl(x - \frac{b + a}{2}\biggr)^2\frac{1}{b - a}\mathrm{d}x \\
&= \left.\frac{1}{3(b - a)}\biggl(x - \frac{b + a}{2}\biggr)^3\right|_a^b \\
&= \frac{1}{3(b - a)}\Biggl[\biggl(\frac{b - a}{2}\biggr)^3 - \biggl(\frac{a - b}{2}\biggr)^3\Biggr] \\
&= \frac{1}{3}\biggl(\frac{b - a}{2}\biggr)^2
\end{align}
$$

Substitute $\displaystyle \text {tol.}\equiv \frac{b-a}{2}$, and solve:

$$\sigma = \sqrt{\frac 13 \cdot {\rm tol.^2}}= \frac{\rm tol.}{\sqrt {3}}$$

