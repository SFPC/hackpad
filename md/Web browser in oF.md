# Web browser in oF

There are several ways to communicate with web from openFrameworks. One of the most radical way is having a browser itself inside oF application. It means you can make communications between C++ and Javascript inside openFrameworks.

It doesn't so make sense if you simply create an application with Javascript instead of C++ but it can be useful when you want to combine oF with a web-based application which already exists for some specific purposes such as:

*   to control Arduino from nodejs on heroku server via openFrameworks ( but if you want to directly communicate with nodejs, maybe [this](https://github.com/satoruhiga/ofxNodejs) is simpler)
*   to access web-API with Javascript libraries while using an hardware interface which cannot be handled by a browser

----

**Set up**

**1. Get Awesomium**

[Awesomium](http://www.awesomium.com/) is a [Chromium-powered](http://www.chromium.org/) HTML UI engine which can be used when you want to make a browser application in C++ or .NET application.

To use in openFrameworks, you need at first [download Awesomium](http://www.awesomium.com/download/) and install it. You can use it for free unless you get more than $100k revenue.

**2. Get ofxAwesomium addon**

There are several ofxAddons for Awesomium but I used [ofxAwesomium](https://github.com/mpcdigital/ofxAwesomium) You need to do a little setup as described in README.md on the github.

When I manually import the addon, your addons directory in XCode looks like this:

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_ZlJOopgPHXi_p.257357_1416886638731_%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%202014-10-28%203.50.46.png)

You need to get and place Awesomium.framework from /Library/Frameworks/Awesomium.framework .

----

**How to use**

You can check examples in addons at first. And here are things I needed to figure out from outside of the examples.

**Sample code**:

[](https://github.com/yukiy/browser-in-OF-basic)[https://github.com/yukiy/browser-in-OF-basic](https://github.com/yukiy/browser-in-OF-basic)

**a.Read html/js/css files**

*   Open a webpage.

*   void testApp::setup(){
*       browser.setup(ofGetWidth(), ofGetHeight());
*       browser.loadURL("[](http://www.google.com)[http://www.google.com](http://www.google.com/)");
*   }

*   Load local html files.

*   void testApp::setup(){
*       browser.setup(ofGetWidth(), ofGetHeight());  
*       browser.loadURL("[](file:///Workspaces/openFrameworks/of_v0.8.4_osx_release/apps/SFPC/browser/bin/data/www/test.html)[file:///Workspaces/openFrameworks/of_v0.8.4_osx_release/apps/SFPC/browser/bin/data/www/test.html](file:///Workspaces/openFrameworks/of_v0.8.4_osx_release/apps/SFPC/browser/bin/data/www/test.html)");  
*   }

*   or you can directly write HTML here.

*   void testApp::setup(){
*       browser.setup(ofGetWidth(), ofGetHeight());
*       browser.loadURL("data:text/html,<h1>Hello World</h1>");
*   }

---

**b. Excute Javascript from openFrameworks**

*   When I press a key, change bgColor of HTML.

*   void testApp::keyPressed(int key){
*       browser.keyPressed(key);
*       browser.doJavaScript("document.body.bgColor = '[#FF0000](https://hackpad.com/ep/search/?q=%23FF0000&via=ZlJOopgPHXi)';");
*   }

*   And also you can load JS file with ofBuffer.

*   void testApp::keyPressed(int key){  
*       browser.keyPressed(key);  
*       ofBuffer buffer = ofBufferFromFile("www/test.js");  
*       browser.doJavaScript(buffer);  
*   }  

---

**c. Access variables in Javascript from openFrameworks**

*   If I want to get a global variable called “g_data” in javascript.

*   void testApp::mousePressed(int x, int y, int button){
*       browser.mousePressed(x, y, button);
*       JSValue data = browser.doJavaScript("g_data");
*       cout << data.ToString() << endl;
*   }

For more methods:

[](http://wiki.awesomium.com/general-use/introduction-to-javascript-integration.html)[http://wiki.awesomium.com/general-use/introduction-to-javascript-integration.html](http://wiki.awesomium.com/general-use/introduction-to-javascript-integration.html)

↑this is for native C++, so good to see "src/ofxAwesomium.cpp" too.

*   Also, there's CEF (another chrome project) and webkit -- for webkit, see [](https://github.com/admsyn/FITC-2014-slides/blob/master/src/ofxPresent/src/ofxPresentApp%2BCocoa.mm)https://github.com/admsyn/FITC-2014-slides/blob/master/src/ofxPresent/src/ofxPresentApp%2BCocoa.mm for osx code to put html content on the screen. (it's literally on the screen, not in a texture).  I don't have good luck with CEF to texture, but the CEF window system works well.  Finally, you can use the CEF syphon client to put a web page into OF via syphon.
*   Also -- see things like this [](https://code.google.com/p/oflivecoding/)https://code.google.com/p/oflivecoding/ that use javascript interpreter but not a browser to open up live coding to OF -- it's javascript based