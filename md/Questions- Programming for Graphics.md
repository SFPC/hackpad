# Questions: Programming for Graphics

started piling up questions concerning Programming for Graphics + general topics around it, since 2013-10-30.

To find unsolved questions: search: (waiting for answer...)

*   2013-11-13 (Wed)

**9. Optical flow example?**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_lrzPpxSUTLN_p.77282_1384994436048_IMG_0182.JPG)

I took a picture of every page of a flip book. I want to use the features in this picture as an emitter of my particle system. Do you have some optical flow examples except ofxCv example?
<undefined><li>**Answer**</li></undefined>

*   Julapy's example (couldn't find on forum, but received it from Zach)

*   2013-11-12 (Tue)

**8. SVG path order / path planning for our plotter**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_lrzPpxSUTLN_p.77282_1384988669382_スクリーンショット 2013-11-20 午後6.03.33.png)

I typed "SFPC" in illustrator, and then I exported it as a svg file. I want to draw the font outline with a single stroke but the path order is scattered because the order depends on the font data.  

I want to draw SFPC using our plotter. How can I define the stroke?

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_lrzPpxSUTLN_p.77282_1384992583365_photo.JPG)
<undefined><li>**Answer**</li></undefined>

*   [A* search algorithm](http://en.wikipedia.org/wiki/A*_search_algorithm) (answer from Kyle)

*   2013-11-9 (Sat)

**7. What is ofDisableArbTex() ?**

ofTexture.h

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_lrzPpxSUTLN_p.77282_1384041520450_Screen Shot 2013-11-09 at 6.56.33 PM.png)

After searching ofGetUsingArbTex() in Xcode project, I understood bUsingArbTex is used for whether using GL_TEXTURE_RECTANGLE_ARB or GL_TEXTURE_2D. 

In short, ofDisableArbTex() means "we don't want to use the part of texture, but want to use whole of texture image".... is it correct? 
<undefined><li>**Answer**</li></undefined>

GL_TEXTURE_2D = pow2 texture.  16x16, 256x64, 128x8, etc.  width and height must be power of 2.  For non power of 2 image (640x480) this is problematic since we are using a sub texture (portion) and not the whole image.  in GL_TEXTURE_2D, gl texture coordinates are in %s, ie (0-1). 

GL_TEXTURE_RECTANGLE_ARB = rectangular texture, width height can be any size.  texture coordinate are in pixels

GL_TEXTURE_2D allows repeating textures and other things, GL_TEXTURE_RECTANGLE_ARB is more space efficient. 

in OF we use GL_TEXTURE_RECTANGLE_ARB when we can, since it's more easier to manage.   ofDisableArbTex() forces OF to use GL_TEXTURE_2D instead of trying to use GL_TEXTURE_RECTANGLE_ARB.  This is useful if you need features unique to GL_TEXTURE_2D or specific shaders (in glsl the code varies if you are using GL_TEXTURE_2D or GL_TEXTURE_RECTANGLE_ARB).

*   2013-11-8 (Fri)

**6. Texture Example**

Today's result: texture + dof + discarding some pixels using fragment shader

*

[](http://code-check-eins-zwei.tumblr.com/post/66401894895/dof-circle-discard-texture)http://code-check-eins-zwei.tumblr.com/[post/66401894895/dof-circle-discard-texture](http://code-check-eins-zwei.tumblr.com/)

I still don't understand what kind of texture Zach was using when Zach show me the dof example. Would you show me it? or, please tell me what kind of texture is looks interesting for point sprite+alpha blending.
<undefined><li>**Answer**</li></undefined>

it's just a distance formula generated texture, I think I used powf to make it curve slightly differently:   [](http://pastebin.com/FbWAicBa)http://pastebin.com/FbWAicBa

from there, be sure to enable point sprite: 

*      glDisable(GL_DEPTH_TEST);

        glEnable(GL_BLEND);

        glBlendFunc(GL_SRC_ALPHA, GL_ONE);

        glEnable(GL_ALPHA_TEST);

        glAlphaFunc(GL_GREATER, 0);

        tex.bind();

and make sure your fragment shader can handle it: 

uniform sampler2D texture;

void main() {

        gl_FragColor = texture2D(texture, gl_PointCoord) *gl_Color;

}

*   2013-11-4 (Mon)

**5. Vertex Shader Ideas?**

Recently I make my particle system + OSC interface + UI (MaxMSP). The goal is that drawing something using only white dot.

Today I added vertex shader to change the point size to realize the distance from camera to each point.

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_lrzPpxSUTLN_p.77282_1383629733037_スクリーンショット 2013-11-05 午前0.28.55.png)

Let me know if you know some common/interesting technics or expression using vertex shader (not the other kind of shaders!)
<undefined><li>**Answer:**</li></undefined>

*   vertex shader can use camera info to control size / color / opacity (ie, DOF)

        *   for DOF see here: [](http://pastebin.com/KJaaWCeH)http://pastebin.com/KJaaWCeH
    *   uses a simple formula to adjust size based on distance from focal plane: float size = abs(gl_Position.z - focusDistance) * aperture + 1.;)

*   vertex shader can animate points using noise functions (as offsets / displacement from the vertice)
*   vertex shader can alter normals (for adjusting lighting, etc or passing data to frag shader)
*   vertex shader can move points around based on some properties

**4. How to implement sin( ofGetElapsedTimef() ) in Max?**

except using MSP...
<undefined><li>**Answer:**</li></undefined>

(waiting for answer...)

*   2013-10-31 (Thu)

**3. Smart way to send values from Max to ofVec3f via OSC?**
<undefined><li>**Answer:**</li></undefined>

Max: using 'pack' or 'pac' object

OF: using ofxKeyValueOSC [](https://github.com/satoruhiga/ofxKeyValueOSC)https://github.com/satoruhiga/ofxKeyValueOSC

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_lrzPpxSUTLN_p.77282_1383585191150_スクリーンショット 2013-11-04 午後0.12.57.png)

*   2013-10-30 (Wed)

**2. MaxMSP bpatcher doesn't load subpatch when I open the main patch**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_lrzPpxSUTLN_p.77282_1383186664087_10.09.38.png)
<undefined><li>**Answer:**</li></undefined>

adding file search path from Window >> File Preference

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_lrzPpxSUTLN_p.77282_1383188483850_11.00.32.png)

**1. linecap in OpenGL?**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_lrzPpxSUTLN_p.77282_1383186230570_7.55.29.png)

By default, OF draws the line looks like rectangle when I call ofLine. I want to draw lines using linecap. I couldn't found any options in OpenGL about linecap. How can I do this? Should I make outline path of capped line?
<undefined><li>**Answer:**</li></undefined>

This is a hack but what if you draw an ofCircle(lineEnd.x, lineEnd.y, lineWidth / 2); ?

↑ Yes I think it might work, but it might be not handy.

I found ofxFatLines by Roy [](https://github.com/roymacdonald/ofxFatLines)https://github.com/roymacdonald/ofxFatLines. should I do this kind of approach...?

*   thick lines opengl is always a HUGE issue
*   [](https://github.com/roymacdonald/ofxFatLines)https://github.com/roymacdonald/ofxFatLines (but this has some bugs at different sizes.  I am not 100% convinced -- for example [](http://i.imgur.com/ApggE.png))http://i.imgur.com/ApggE.png)...  vase render has updates, maybe it's improved since this addon?   I still feel unconvinced it can handle edge cases well. 
*   fake smooth lines [](https://github.com/apitaru/ofxSmoothLines)https://github.com/apitaru/ofxSmoothLines
*   graphics libraries, like CAIRO do great 2d lines, but they are not 3d oriented.
*   I like this one: [](https://github.com/bgstaal/ofxShivaVG)https://github.com/bgstaal/ofxShivaVG ( << cool!!)

        *   uses stencil buffer, pay attention to main.cpp

*   for NON variable thickness lines, I can show you how to calculate end caps yourself...  it's not hard...  use the circle formula.  