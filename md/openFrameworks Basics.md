# openFrameworks Basics 

**Questions**

*   How do I get started with OF?
*   Best way to structure files, especially if you are trying to put it on the Github and keep on updating?
*   How to Addon stuff?
*   Where and how can we find examples?
*   how to use, understand and navigate through the documentation

**Notes:**

*   **How compiling works? **

1.  **Source code - Write text **

        1.  differene between cpp file and h file

                1.  **h file** - list of ingredient
        2.  **cpp file** - how to execute the ingredients (steps)

2.  **Pre-process**

        1.  Taking the text and changing it 

                1.  "#" Take this file and modify it
        2.  Include guard so if the file sees "h" file twice, it won't freak out

                        1.  [](http://en.wikipedia.org/wiki/Include_guard)http://en.wikipedia.org/wiki/Include_guard

3.  **Compile**

**documentation: **

use the prefix "of" to know what's going on

objects will have an of, like ofImage, ofPolyline, ofVideoPlayer but have function and variables that don't have OF as a prefix.  like: 

ofImage img;

img<u>.draw();</u>

other functions like in ofGraphics, such as ofRect, ofLine, ofCircle start with "of" as a prefix and don't require an object. 

examples are really your friend.  