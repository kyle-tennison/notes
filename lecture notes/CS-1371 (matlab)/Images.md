# Images

## Fundamentals

```MATLAB
img = imread(filename) % You get a 3D array from this

% The last dimension is your R, G, B "layers"
% For indexing, you now do
pixel = img(r, c, layers)

% You can use this to extract different colors
red_pixels = img(:,:,1)

% To show a modified image, you can use `imshow`
imshow(red_pixels)
```

Using `imgshow()` will display the image in a special image-viewing window, whereas `image()` will put the image into a scaled plot, usually distorting it.

> 🤖 (notecheck comment) - The function name "imgshow()" is incorrect. The standard function name in MATLAB is "imshow()".

### Elementary Operations with Indexing

You can flip an image by reversing the columns or rows (depending on which axis you want to flip about). 

### uint8 Math

Image values are unsigned 8-bit integers, and MATLAB will automatically ceil or floor values greater than 255 or less than 0 to fit within the bounds. 

You can cast doubles into uint8 types using the `uint8` function. Again, values outside of the range will clip to the nearest bound.

When performing math on an image, all double values need to be cast back into uint8 types. Division and multiplication continue to work for uint8—the *products are rounded* instead of being converted into floats.

## Image Modifiers

You can **resize** an image using `newImg = imresize(imgArr,[newRows,newCols])`

You can *move the black pixels from one image to another* using `moveBlackPixels('img1.png','img2.png')`

You can **green screen** an image and place it atop another image using: `greenScreen('greenscreen.png','backdrop.jpeg')`

You can **rotate** an image using: `newimg = imrotate(img,angle)` (angle in degrees)

You can convert a 3-layer image into a 1-layer **grayscale** image using `newImg = rgb2gray(img)`

## Random Tricks

You can get the negative of an image with `img = 255 - img`

If you want to transpose an image, you have to transpose each layer first, then concatenate them back:

```MATLAB
% Separate into layers
r = img(:,:,1);
g = img(:,:,2);
b = img(:,:,3);

% Transpose and concatenate back
newImg = cat(3, r', g', b');
```

This `cat` function can be used to concatenate in 3D. Another example is:
```
img = imread('serena.jpg');

grayImg = rgb2gray(img); % 1-layered array
grayImg = cat(3, grayImg, grayImg, grayImg); % Stack layers to make 3 layers
```