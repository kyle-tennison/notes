# Convolutional Neural Networks

Convolutional neural networks (CNN) are [Feedforward NNs](Feedforward%20NN.md) under the [Deep Learning](Deep%20Learning.md) class; they are "the de-facto standard in deep learning-based approaches to computer vision." 

New architectures, such as the transformer, are replacing CNNs in image cognition. 

At the core, you:
1. Run a [Convolution](Convolution.md) on some input image with a few different kernels. Each kernel will yield a new matrix—so you end up with (on the order of) 32 convolved images. These are called "layers," so 32 layers corresponds to 32 convolved images.
2. Downsample each of these convolved images—that is, reduce the resolution. This process is called **pooling**. Max Pooling is often used: split the image into squares (e.g., 2px by 2px) and select the highest value pixel from that square & discard all other pixels. Usually, each downsample increases the number of layers, so you get more yet smaller images.
3. Convolve the downsampled image with new kernels.
4. Repeat steps 2 & 3 until the "image" is a single pixel
5. Arrange these pixels into a [Multilayer Perceptron](Multilayer%20Perceptron.md). 

Then, using [Back Propagation](Back%20Propagation.md) you can train this Perceptron and the kernels used.




### Resources

```vid
https://www.youtube.com/watch?v=pj9-rr1wDhM
Title: Convolutional Neural Networks Explained (CNN Visualized)
Author: Futurology — An Optimistic Future
Thumbnail: https://i.ytimg.com/vi/pj9-rr1wDhM/mqdefault.jpg
AuthorUrl: https://www.youtube.com/@OptimisticFuturology
```




