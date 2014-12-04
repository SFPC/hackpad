# Zach's OF Workshop

## OF

**History**

**Philosophy**

*   DIWO - do it with others
*   Simplicity
*   consistant and intuitive naming convention
*   cross platform - can compile for multiple devices
*   powerful - utilize existing libraries
*   extendable - ofx addons

**Resources**

*   forum.openframeworks.cc - the library/toolkit is an entry point but the people using it and the community is more powerful.
*   tutorials (on tutorial page) and books 
*   mastering openframeworks book
*   the Japanese book - great code examples and graphics, who needs the text... ;-) 
*   [auckland openframeworks ](https://sites.google.com/site/ofauckland/people/colab-auckland)site has small code examples  
*   there is a [book on GitHub](https://github.com/openframeworks/ofBook) that is currently being written
*   [vimeo](http://vimeo.com/tag:openframeworks) & [flickr](https://www.flickr.com/groups/openframeworks/) for inspiration or [forum/examples](http://forum.openframeworks.cc/category/examples)
*   OF notes here: [](http://www.jeffcrouse.info/teaching/intermediate-of/)http://www.jeffcrouse.info/teaching/intermediate-of/
*   [](http://www.jeffcrouse.info/teaching/code-for-art/)http://www.jeffcrouse.info/teaching/code-for-art/

**C++**

*   Process 4 steps

        *   text

                *   .h & .cpp
        *   .h = header (e.g. table of contents - it's like a map for the compiler)
        *   .cpp = implementation (e.g. the text of the book)

        *   pre-process

                *   "#" this symbol will define specific rules for the target it will be compiled for
        *   most important one is "#include "ofMain.h"" which says 'take allllll the text in all of the h files and put it in here' *called an include guard
        *   when your program can't find a file it is a problem at this level

        *   compile

                *   .cpp -> .o
        *   does not care about your .h files!!!!!!!   (the h files are put into .cpp files in preprocess)
        *   different settings so you can compile and debug or compile and release
        *   compiling creates lots of 'o' files that will reference each other 

        *   link

                *   takes allllll the .o files and smashes them together to make one file

*   helpfull places 

        *   cplusplus.com
    *   a few books in the library
    *   c & c++ in five days - [pdf](https://www.box.com/shared/static/qqtm40rory.pdf) 
    *   use existing code

*   Folder structure

        *   There are different folders inside libs, libraries that come with it that do cool things (fmod, freetype, rtaudio -low level audio-, etc). oF comes with some curated libraries.
    *   Inside the library 'openframeworks', there are a bunch of core folders that can give you a good idea of the main _design philosophy ;)_ of the language (math, gl, 3d, etc). 
    *   openFrameworksCompiled is where the built core of oF can be found

                *   Raspberry Pi compile for oF takes a long time!

        *   Scripts: shell scripts or templates for making projects. 
    *   Random folders like other - small processing sketch for serial? Export - things that get added to your project after it is compiled. 
    *   Docs: general documentation 
    *   Changelog: useful to look at what's changing - see what priorities and history are. Document is a pretty fast way of seeing what the activity is. 

                *   *love the notation, '+' is new features, '-' is removed and '/' are changes

        *   Examples are sorted by topic - examples about math, using noise, trig, libraries about sound, both high and low level sound work. 
    *   <u>Go through and compile them</u>. Take a look at them - can find a lot of things. Try to ship with a lot of examples, which become a way of digging into things you like in the code. 
    *   Addons - additional libraries. A lot of people wanted different things, some people wanted 3D, XML, CV, if you add everything to the core, the core library gets too big, which is hard to maintain. Means projects will also be very big! Additional code that you can add to a project - think about them as mini-libraries. They could be small but also really complex. A simple example - a vector graphics addon for saving postscript. 

*   Make a new Project

        *   Tool - project generator application, a GUI for letting you adjust properties of a sketch as well as select addons. You can say where the sketch goes - recommend putting them inside of <u>apps > myapps</u>. 
    *   When creating a project with the project generator, you can name it whatever and select addOns that you want to use in it. 
    *   You'll be able to add more addOns later on.
    *   in OSX: dependencies - need to select what target you're using - Debug vs. Release - you want to build debug project. 

                *   ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Ag0nPcx0dAw_p.252113_1413903188738_undefined)

*   Questions

        *   Why is there no main.h?

                *   main is an entry point, its job in life is to run code - just read and do things but <u>every program needs a place to start and this is it</u>. 
        *   [](http://en.wikipedia.org/wiki/Entry_point)http://en.wikipedia.org/wiki/Entry_point
        *   No other code calls main, so there doesn't need to be an .h file for main. 
        *   Here, main() sets up a window and calls ofRunApp and repeatedly calls draw/update functions
        *   You typically don't alter main, but there are instances where you want to change it, for example, the size of the window.

        *   Majority of code you write is in ofApp (used to be testApp? before that triangleApp? -- you'll see these if you download older example code) - this is your root level, the thing that is  running. There's a trick happening here similar to Processing (they don't show it to you) - here in oF, we've created an object, ofApp, this extends ofBaseApp (takes the recipe of ofBaseApp and extends it). In Processing, there's an object called PApplet and you are running your own version of setup and draw. 

                *   BaseApp already exists. ofApp is our extension of BaseApp

*   void ofApp::setup(){
*   ofSetVerticalSync(false);
*   }