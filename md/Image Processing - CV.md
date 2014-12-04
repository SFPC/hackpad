# Image Processing & CV

**We use examples from this repo: [](https://github.com/ofZach/sfpc_image_cv)https://github.com/ofZach/sfpc_image_cv**

The basic paradigm is like a funnel. Taking a lot of information and reducing it. Imagine a 1920x1080px image * 255 values – that's a lot of information. 

There are a few (informal) categories in this category: 

*   'Brute force' approaches – for loops marching through images. 
*   Image Processing – comparing pixels to their neighbors etc. 
*   Computer vision – comparing multiple images, persistence, video etc.

For example, in the field of computational photography there is a new camera app from Google that goes from a sequence of images back to an image. Allowing the user to selectively focus. This uses a technique called SfM (structure from motion.)

[](http://googleresearch.blogspot.com/2014/04/lens-blur-in-new-google-camera-app.html)http://googleresearch.blogspot.com/2014/04/lens-blur-in-new-google-camera-app.html

[](http://jabtunes.com/labs/lensblur/index3.html)http://jabtunes.com/labs/lensblur/index3.html

Typically you begin this with greyscale images. Think of a color image as three (interleaved) images in red, green & blue. 

In Photoshop go to Filter>Other>Custom. This allows you to see how these filters often work. 

A kernel – basically a box of numbers. Looking at a pixel and it's neighbors. Typically they are odd numbered with the pixels around it. 

![](https://wiki.hexagongeospatial.com/images/1/1c/Enhance_spatial_convolution_kernel_1.png)

For example a blur (gaussian) looks like this: 

1       2       1

2      4      2

1       2       1

Viewed in three dimensions it looks something like this: 

![](http://www.emeraldinsight.com/content_images/fig/1270790407028.png)

Whereas a sharpen filter: 

-1      -1      -1 

-1       8     -1  

-1      -1      -1

Other options are finding slopes:

-1      -1      -1 

 0      0      0  

 1       1        1

Vector fields – every pixel in the image is a line. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Agh7ZbiSx4X_p.155968_1398794635460_VectorFields.gif)

How do you convert an image into a vector field? 

Gradient – [having a tough time describing it]

Jeremy Rotsztain

[](http://www.mantissa.ca/projects/obsessions.php)[http://www.mantissa.ca/projects/obsessions.php](http://www.mantissa.ca/projects/obsessions.php)

Thresholding – Like a mask. Using a for loop and determining for a given pixel whether it is above or below a threshold. 

Typical assignments Zach gives are to take an image and apply the following:

*   1. Threshold it
*   2. Find the centroid
*   3. Squarepacking
*   4. Find connected components

It is helpful to know the concept that even if we can describe it as a 2D array it is important to understand that it is really stored as a single array. 

We then covered a host of different areas:

*   Push & popMatrix
*   Background subtraction
*   Taking two different images and comparing their absolute difference. 

**Book/Article Recommendations:**

_Digital Image Processing_ – Gonzales & Woods [](http://www.imageprocessingplace.com/)http://www.imageprocessingplace.com/

_The Pocket Handbook to Image Processing Algorithms in C - _Myler and Weeks

_Computer Vision: Algorithms and Applications _- [Richard Szeliski](http://research.microsoft.com/~szeliski), Microsoft Research

*   [](http://research.microsoft.com/en-us/um/people/szeliski/publications.htm)http://research.microsoft.com/en-us/um/people/szeliski/publications.htm
*   [](http://szeliski.org/Book/)[http://szeliski.org/Book/](http://szeliski.org/Book/) for author website. Free download of book [here](http://szeliski.org/Book/drafts/SzeliskiBook_20100903_draft.pdf) as pdf.

article: _Computer Vision for Artists and Designers: Pedagogic Tools and Techniques for Novice Programmers _[](http://flong.com/texts/essays/essay_cvad/)http://flong.com/texts/essays/essay_cvad/

chapter: Golan's 30% done chapter on CV and OpenFrameworks [](https://github.com/golanlevin/ofBookChapter/blob/master/main.md)https://github.com/golanlevin/ofBookChapter/blob/master/main.md

_Programming Interactivity: A Designer's Guide to Processing, Arduino, and openFrameworks - _Joshua Noble. I found it online on scribd [here](http://www.scribd.com/doc/63761742/Programming-Interactivity-A-Designer-s-Guide-to-Processing-Arduino-and-Openframeworks).

nancy burson did amazing work with early composite photographs and computational approaches to mixing images

[](http://nancyburson.com/composite-silver-prints/)[http://nancyburson.com/composite-silver-prints/](http://nancyburson.com/composite-silver-prints/)

jason salavon has some great projects with image averaging: 

[](http://www.salavon.com/)[http://www.salavon.com/](http://www.salavon.com/)

ken knowlton was doing computer assisted mosiacs: 

[](http://www.knowltonmosaics.com/)[http://www.knowltonmosaics.com/](http://www.knowltonmosaics.com/)

I helped him with this game: 

[](http://www.creativeapplications.net/games/jigazo/)[http://www.creativeapplications.net/games/jigazo/](http://www.creativeapplications.net/games/jigazo/)

chris jordan is doing more modern images w/ mosiacing: 

[](http://www.chrisjordan.com/gallery/rtn/#silent-spring)[http://www.chrisjordan.com/gallery/rtn/#silent-spring](http://www.chrisjordan.com/gallery/rtn/#silent-spring)

using user interface like pixels

[](http://www.the389.com/)[http://www.the389.com/](http://www.the389.com/)

jk keller has some really nice projects with image processing: 

[](http://jk-keller.com/)[http://jk-keller.com/](http://jk-keller.com/)

Rafael Lozano-Hemmer’s “Homographies"

he makes a lot of relational architecture projects, one of my huge inspiration

[](http://www.lozano-hemmer.com/homographies.php)[http://www.lozano-hemmer.com/homographies.php](http://www.lozano-hemmer.com/homographies.php)

Daniel Rozin’s "wooden mirror"

[](https://vimeo.com/7820888)[https://vimeo.com/7820888](https://vimeo.com/7820888)

classic one. there is one as permanent installation at ITP

Memo worked on this mv

it’s a mix of variety of techniques but the documentation is quite well-writen

[](http://www.msavisuals.com/wombats-techno-fan/)[http://www.msavisuals.com/wombats-techno-fan/](http://www.msavisuals.com/wombats-techno-fan/)

compilation of surveillance computer vision clips

now that you know some of cv techniques, what techniques are being used here

[](https://vimeo.com/36239715)[https://vimeo.com/36239715](https://vimeo.com/36239715)