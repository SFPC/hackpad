# Shaders are fun

Check out typing.io!

The following code goes in your bin/data folder

Here is the code for the vertex shader "bin/data/shader.vert"

*   void main(void)
*   {
*       gl_TexCoord[0] = gl_MultiTexCoord0;
*       gl_Position    = ftransform();
*   }

here is the code for the fragment(pixel) shader "bin/data/shader.frag"

*   #version 120
**   void main( void )
*   {
*       float width = 1024.0;
*       float height = 768.0;
*           float x = gl_FragCoord.x / width;
*       float y = gl_FragCoord.y / height;
**       
**       float gray = (x * y);
*       
*       
*       gl_FragColor = vec4(gray, gray, gray, 1.0);
*   }
*

for Defne:

**   //--------------------------------------------------------------
**   void ofApp::setup(){
**       shader.load("shader");
****   }
****   //--------------------------------------------------------------
**   void ofApp::update(){
**       ofSetWindowTitle("FPS: " + ofToString(ofGetFrameRate()));
****   }
****   //--------------------------------------------------------------
**   void ofApp::draw(){
**       shader.begin();
**       ofRect(0, 0, ofGetWidth(), ofGetHeight());
**       shader.end();   
****   }
**   Examples:
*   #version 120
**   void main(void)
*   {
*           float width = 1024.0;
*           float height = 768.0;
*           float x = gl_FragCoord.x / width;
*           float y = gl_FragCoord.y / height;
**           float gray;
**           if (sin(x * 80) > cos(y * 50)) {
*                   gray = tan(sin((x * y) * 40.0) * 34.0);
*           } else {
*                   gray = tan(y + x);
*           }
**           gl_FragColor = vec4(gray, gray, gray, 1.0);
*           //gl_FragColor = vec4(1.0, 0.0, 0.0, 1.0);
*   }

Defne's Shader:

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_TXqZi99eYWa_p.260528_1417733079151_Screen Shot 2014-12-04 at 5.43.47 PM.png)

code:

#version 120

void main( void )

{

    float width = 1024.0;

    float height = 768.0;

        float x = gl_FragCoord.x / width;

    float y = gl_FragCoord.y / height;

    float red, green, blue;

    if (x > 0.5) {

        red = sin(x * (40 * x *x));

        green = sin(x * (20 * x *x));

        blue = sin(x * (10 * x *x));

    }

    gl_FragColor = vec4(red, green, blue, 1.0);

}

another:

#version 120

void main(void)

{

        float width = 1024.0;

        float height = 768.0;

        float x = gl_FragCoord.x / width;

        float y = gl_FragCoord.y / height;

        float red, green, blue;

        if (tan(x * 30) > cos(y * 50)) {

                red = sin(x / (y + 1));

                blue = cos(y - x);

                green = tan(x);

        } 

        else {

                red = tan(y + x);

                blue = cos(sin(x * y));

                green = sin(tan(x + y));

        }

        gl_FragColor = vec4(red, green, blue, 1.0);

        //gl_FragColor = vec4(1.0, 0.0, 0.0, 1.0);

}