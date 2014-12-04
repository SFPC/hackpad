# Binary Numbers (Oct. 2)

There are ten types of people in the world, those that know binary ad those that don't. (Anon)

All data, images... are illusions encoded in 0's and 1's 

(*summarized paragraph from Hal Abelson, Ken Ledeen, Harry Lewis in "Blown to bits")

Photoshop & Audicity experiment 

1) make an image in PS w 50% gray and save it as raw

2) open audicity and import 'as raw' the image you just made as unsigned 8-bit mono

*   notice it is imported as one straight line as the image file is being interpreted line by line - the solid color has no variation so it is a straight line 

3) back in photoshop ad noise to the image and resave then import again in audicity

*   notice the pattern when you open it
*   try again manipulating the image by hand " :) "
*   the frequency you hear is caused by the width of the image

Signaling System

*   it's a way to encode data through numbers much like morse code or the 'fax machine' game we played on day one
*   Hannah Weiner, 'Code Poems' - used the international flag signals to make poems and also to translate existing works like romeo and juliet 

        *   [](http://monoskop.org/images/a/ab/Weiner_Hannah_Code_Poems.pdf)http://monoskop.org/images/a/ab/Weiner_Hannah_Code_Poems.pdf
    *   her work is here also [](http://www.youtube.com/watch?v=DF0IoXUGkKU)http[://www.youtube.com/watch?v=DF0IoXUGkKU](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0CCAQtwIwAA&url=http%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DDF0IoXUGkKU&ei=XWctVOO7CMLIsASc9IG4DA&usg=AFQjCNEYHd2OhzJKwebJ9DWmGJ75ptc-3A&sig2=zznTn6BLh_rTvz2OngPeHg&bvm=bv.76477589,d.cWc)

*   Binary can also be thought of as information display (ex: candle in the window, one if by land and two if by sea and none if they are not coming)

Counting in binary

*   groups of 8, 'xxxxxxxx' some are more significant then others as the one on the far left changes the overall number in a significant way whereas the number on the far right has little change in the number ex '11111111 = 255 and 01111111 = 127'

        *   binary numbers debug tool

*   "signed bit", you may have one of the bits represent something significant like a negative. Ex: the most significant bit could represent negative 

image example: 

*   white is always 255, but looking at the differences between images the contrast between changes is more severe when a significant value is changes because the change is larger (black vs white) where as the changes in images with a lower significance you see more noise but the changes are more minute and less dramatic
*   ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_VCZ2oGTI1sx_p.252113_1412264981240_undefined)

Binary as permutation

*   'Every Icon' by John F. Simon: [](http://www.numeral.com/eicon.html)http://www.numeral.com/eicon.html - applet w/ 32x32 grid that will run through every combination of what can be represented in that grid. The idea is that at some point your face will be shown, anything will be shown at least once. 
*   Every Unicode by Joerg Piringer - [](http://joerg.piringer.net/index.php?href=unicode/unicode.xml)http://joerg.piringer.net/index.php?href=unicode/unicode.xml & [](http://www.youtube.com/watch?v=Z_sl99D2a18)http://www.youtube.com/watch?v=Z_sl99D2a18
*   Chris Harrison, Lumitrak - [](http://chrisharrison.net/index.php/Research/Lumitrack)http://chrisharrison.net/index.php/Research/Lumitrack
*   Roman Olpaca - [](http://www.juxtapoz.com/current/one-canvas-count-from-1-to-56m)http://www.juxtapoz.com/current/one-canvas-count-from-1-to-56m
*   Arthur Ganson - machine w concrete - [](http://www.youtube.com/watch?v=5q-BH-tvxEg)http://www.youtube.com/watch?v=5q-BH-tvxEg

Tools:

*   xxd, command line tool that will take a text file and print it out in binary format

        *   xxd -b filename  (print out binary info)

*   use the mac calculator using 'command 3' to see the binary and ascii values 
*   ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_VCZ2oGTI1sx_p.252113_1412270902394_undefined)![](/static/img/pixel.gif)