# OF Common Compile Errors

**Post Errors here and let's look for common errors to troubleshoot:**

While trying to compile ofxVoronoi example file:  

[](https://github.com/vanderlin/ofxVoronoi)https://github.com/vanderlin/ofxVoronoi

Problem with Compile Utils.cpp

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_ucGMwZ1jU01_p.77236_1414509627560_letterman-top-10.jpg)

TOP 5 problems 

*   set to build openframeworks not the project (target)

        *   soluton : be sure to pick the target you are compiling in the top left corner
    *   ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_ucGMwZ1jU01_p.77236_1414517449580_Screen Shot 2014-10-28 at 1.30.25 PM.png)

*   64 bit vs 32 bit

        *   sometimes it's set to build for 64 bit not 32 bit, you can change this by hightlighting the blue file for the project in the sidebar and adjusting build settings
    *   ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_ucGMwZ1jU01_p.77236_1414517552194_Screen Shot 2014-10-28 at 1.31.38 PM.png)

*   missing frameworks from older projects

        *   older projects (0.8.0 for example) might be missing frameworks needed in newer OF
    *   solution-- navigate to system frameworks, right click to say "reveal in finder" and find the missing frameworks (likely coreVideo and qtkit) and drag them into the older project
    *   ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_ucGMwZ1jU01_p.77236_1414517699758_Screen Shot 2014-10-28 at 1.33.11 PM.png)