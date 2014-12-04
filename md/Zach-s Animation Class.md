# Zach's Animation Class

**Class on github**

here - [](https://github.com/ofZach/algo2012)https://github.com/ofZach/algo2012

**Examples**

Mushroom on an oscilloscope - [youtube](https://www.youtube.com/watch?v=rtR63-ecUNo)

Jerobeam Fenderson - [nuclear black noise](https://www.youtube.com/watch?v=YqSvkNjWnnQ)

John Whitney's use of analogue computers ([video](https://www.youtube.com/watch?v=5eMSPtm6u5Y)) ([wikipedia](http://en.wikipedia.org/wiki/John_Whitney_(animator))) ([catalog 1961](https://www.youtube.com/watch?v=TbV7loKp69s)) - made the graphics manually (math/by hand) and photographed them on the computer then animated them ([vertigo title sequence](http://rhizome.org/editorial/2013/may/9/did-vertigo-introduce-computer-graphics-cinema/)) ([permutations](https://www.youtube.com/watch?v=BzB31mD4NmA))

lissajous - [](http://en.wikipedia.org/wiki/Lissajous_curve)[http://en.wikipedia.org/wiki/Lissajous_curve](http://en.wikipedia.org/wiki/Lissajous_curve)

**sine and cosine**

...think of the dot moving around the circle

*   sine follows the height of the dot
*   cosine follows the movement back and forth of the dot

example in OF

*   sin thinks in radiants so every 6.28 seconds it will repeat (2 pi)

*   void ofApp::draw(){
*       ofBackground(0,0,0);
*       
*       float pct = (sin(ofGetElapsedTimef()) / 2.0) + 0.5;
*       cout << pct << endl;
**       float xPos = 250;
*       ofCircle(xPos,250,30);
*   }

*gives us the small numbers (see in debug). you can convert to percent and remap to scale and offset to get big numbers (replace line 7)

*   float xPos = 300 + pct * 200;

This is the long way, a short way to do it is 

*   float xPos = ofMap( sin(ofGetElapsedTimef()), -1, 1, 300, 500);

Can make it go faster by adding this

*   float xPos = ofMap( sin(ofGetElapsedTimef()*15), -1, 1, 300, 500);

**Combining sine waves**

...using volume to turn the 'frequency' of the other sine

*   carrier - the underlying frequency
*   modulator - the frequency that is changing the carrier

*   code here...

[Zach Lieberman](/ep/profile/AUZb6pnTdHj)

**Moving sine and cosinein a circle**

X = xorig + r * cos(angle)

y = yorig + r * sin(angle)

*   ...code example...

*   in OF you'll see the sin represented as '-sin', its because 0,0 is the top left corner
*   hard to see what is happening but can record the path the cursor to see the movement

*   ...code example...

At this point he goes into week [4 & 5 of the git hub examples](https://github.com/ofZach/algo2012/tree/master/week4)

*   next week - 'atan' lines, magnitude (how long the line is) & orientation (angle) 

**Homework from 10/27**

*   Create your own John Whitney art using sine & cosine
*   make a creature, can it breathe - can it have wings

**Useful resources**

CODING MATH youtube channel. The guy is using very basic javascript so it's also good for learning basic js stuff.

[](https://www.youtube.com/channel/UCF6F8LdCSWlRwQm_hfA2bcQ)[https://www.youtube.com/channel/UCF6F8LdCSWlRwQm_hfA2bcQ](https://www.youtube.com/channel/UCF6F8LdCSWlRwQm_hfA2bcQ)

You can find Trigonometry in video lessons 1 to 5 and easing in lessons 27 and 28.