# PS3 Eye camera with OpenFrameworks

Notes on getting the PS3 Eye camera working with OF:

(note, you do *not* need macam installed, this works on any mac w/ out macam.... just tested) 

*   <s>Download the "Looking for the latest version? maccam-cvs-build-2009-09-25.zip" at the top of this page:</s>

*   [](http://sourceforge.net/projects/webcam-osx/files/cvs-build/)<s>http://sourceforge.net/projects/webcam-osx/files/cvs-build/</s>

*   <s>Copy the ".component" file into Macintosh HD/Library/QuickTime</s>

*   <s>Download Jon Wohl's fork of ofxMacamPs3Eye:</s>

*   [](https://github.com/jmwohl/ofxMacamPs3Eye)<s>https://github.com/jmwohl/ofxMacamPs3Eye</s>
*   The pull request for the minor change I made was merged back in to the original repo:
*   [](https://github.com/paulobarcelos/ofxMacamPs3Eye)https://github.com/paulobarcelos/ofxMacamPs3Eye

*   Add that to your "addons" folder in OpenFrameworks and include this in your project

**Using the camera:**

*   In the header:

*   In the cpp:

    ...etc etc...

if you add this code to another project, you might need to make sure .m files compile as objective-c++ not objective-c (had some linking errors otherwise)

After I changed the Type from Objective-C to Objective-C++, I was able to compile it. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Uk1UmCE7MAN_p.90780_1384471800674_Screen Shot 2013-11-14 at 6.29.23 PM.jpg)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Uk1UmCE7MAN_p.90780_1384471810154_Screen Shot 2013-11-14 at 6.29.34 PM.jpg)

Now I have another error, "Field type 'ofxMacamPs3Eye' is an abstract class"

helpful?  [](http://forum.openframeworks.cc/index.php?topic=10547.0)http://forum.openframeworks.cc/index.php?topic=10547.0

yes. i'm looking at the same page but don't know where to put the following. 

<s>bool setPixelFormat(ofPixelFormat pixelFormat) { return true;}</s>

<s>ofPixelFormat getPixelFormat() { return OF_PIXELS_MONO;};    </s>

<s>void videoSettings() {}</s>

<s>void setVerbose(bool bTalkToMe) {}</s>        <-this didn't work.

I was able to clear the error, "Field type 'ofxMacamPs3Eye' is an abstract class" by doing this. 

In ofxMacamPs3Eye.h

class ofxMacamPs3Eye<s> : public ofBaseVideoGrabber, public ofBaseVideoDraws </s>{

I removed " : public ofBaseVideoGrabber, public ofBaseVideoDraws"

I got this idea from [here](http://forum.openframeworks.cc/index.php?topic=364.15)