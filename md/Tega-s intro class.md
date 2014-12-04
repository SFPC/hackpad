# Tega's intro class

Let's use Processing! [](https://www.processing.org/download/?processing)https://www.processing.org/download/?processing

Helpful guides:

*   API, can also right click on term in interface to see examples here - [](http://www.processing.org/reference/)http://www.processing.org/reference/
*   Search for and ask questions here: [](http://forum.processing.org/two/)http://forum.processing.org/two/
*   extend processing with libraries [](http://processing.org/reference/libraries/)http://processing.org/reference/libraries/
*   online video tutorials - [](http://icm.shiffman.net/)http://icm.shiffman.net/
*   processing for browser - p5js.org

Intro Books on the SFPC Shelf:

*   Learning Processing (Dan Shiffman Intro) [](http://www.learningprocessing.com/)http://www.learningprocessing.com/
*   The nature of code - [](http://natureofcode.com/)http://natureofcode.com/
*   Processing Handbook (Reas and Fry)
*   Visualizing Data (Fry)
*   Interactivity (Processing, OF and Arduino)
*   Think Like a programmer (intro to python)

Huge amount of Processing code available here:

*   [](http://www.openprocessing.org/sketch/159778)http://www.openprocessing.org/sketch/159778

When you need more then Processing for processing heavy work - [](http://www.openframeworks.cc/)http://www.openframeworks.cc/

**<u>Day 2: Oct. 9th</u>**

Fun with variables! There are two types

*   Global - these are available everywhere in the program
*   Local - these are only available in the bracket it's mentioned in

For loops, what do they do? Lets say you want a program to draw 10 horizontal lines ;-) You could write 10 lines of code with explicit positioning to declare the x and y values on the access e.g.:

*   line(x,y,x1,y1);
*   line (10,10,10,100);
*   line (20, 10,20,100);
*   line(30,10,30,100);
*   line(40,10,40,100);

but if the lines increment by 10 each time you can also write it like this:

*   //here i is a local variable
*   //for (variable type starting value; exit condition;
*   for(int 1=10; i<width; i=1+30){
*     line(i,10,1,100);

For loops also execute the commands so if you have an animation you want to see display on the screen if you put it in a for loop it will show the last frame of the full animation (the result). You then have to draw it out line by line.

*    if (i<width){
*    line(i,10,i,100);
*    i=i+10;

Now we want to draw horizontal lines in addition to the vertical lines.

*   //here i is a local variable
*   //for (variable type starting value; exit condition;
*   for(int 1=10; i<width; i=1+30){
*   for(int j=10; j<height; j=j+10){
*     line(i,10,1,100);
*     line(10,j,200,j);

While loops are also cool, they execute while a certain condition is met like if x<1000.

Different ways to attack a new program

1) look up someone else's code that does something similar and just hack it

2) write out the steps in comments then fill in the code under the comments like

*   //draw a thing
*   //move a thing this way
*   //when i hit a corner turn...
*       (oh shit i don't know how to do this, well... i guess it should)
*       a) know where the corners are
*       b) figure out which way to turn
*   //go a new direction