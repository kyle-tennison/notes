# U Nets


This is used for:
- Upscaling
- Diffusion models
- Image Segmentation
	- This allows you to classify different regions within an image


![[image-36.png]]


This uses an **encoder-decoder** process.

### Encoder

By using a [Convolutional Neural Networks](Convolutional%20Neural%20Networks.md), you follow the typical process of convolution until you get a tiny image.

The resources I find say that it uses a $2 \times 2$ Max Pool downsampler, but I'm not sure if this is always the case.


![[image-37.png]]


When you get to the bottom of the U (shown above), you never actually send the data into a dense neural network. In other words, there are no fully connected layers here; purely convolution.
### Decoder

You use "deconvolutions" aka "transposed convolutions" to upsamples the images. 

The layers from the encoder step are *concatenated with the decoder step* (shown with the gray arrows above). You are simply adding the images from the encoder to the layers in the decoder. This helps with classification of different regions. 

Depending on if the convolution was [padded](Convolution.md#Padding) the output may or may not have the same output resolution as the input image.




## References 

```vid
https://www.youtube.com/watch?v=NhdzGfB1q74
Title: The U-Net (actually) explained in 10 minutes
Author: rupert ai
Thumbnail: https://i.ytimg.com/vi/NhdzGfB1q74/mqdefault.jpg
AuthorUrl: https://www.youtube.com/@rupert_ai
```

```vid
https://www.youtube.com/watch?v=-dfSZ_uLfo8
Title: UNet for Image Segmentation - What You Need To Know! - Computer Vision
Author: Johannes Frey
Thumbnail: https://i.ytimg.com/vi/-dfSZ_uLfo8/mqdefault.jpg
AuthorUrl: https://www.youtube.com/@JohannesFrey
```