# Convolution

Mathematically:

$$f*g = \int_0^tf(\tau)g(t-\tau)d\tau$$

For discrete values, you can think of this as taking a set $f$ and a set $g$ (smaller than $f$) *inverting it* (i.e., flipping its order) and sweeping it across the set f. The result is a larger set, where each value is determined by the product of the overlapping values.



![[aa_copy.gif]]

For example, above, you can see that the product of the over lapping values occurs when the peaks of the kernel and signal align; this gives the greatest result. Because the kernel is nonzero elsewhere, there is some nonzero result near the signal peak. 

The **kernel** refers to the smaller set, and the **signal** refers to the larger set. This is sometimes called a "Filter" or "Feature Detector."


![[same_padding_no_strides.gif]]

Convolution can be done in 2D. Above shows a 3x3 kernel. Each point on this kernel grid has a value; if you multiply this each value by the pixel that it shadows, then take the sum of all constituent kernel grid points, you get the value that is "projected" onto the teal surface above—which would be the convolution. 


### Padding 
You can "pad" the image to ensure that the convoluted output has the same resolution.

![[image-38.png]]


However, this isn't always necessary. 