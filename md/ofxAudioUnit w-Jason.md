# ofxAudioUnit w/Jason

Source code from workshop: [](https://github.com/SFPC/Audio-Unit-Workshop.git)https://github.com/SFPC/Audio-Unit-Workshop.git

**<u>Step 1: Getting set up</u>**

Download ofxAudioUnit : [](https://github.com/admsyn/ofxAudioUnit)https://github.com/admsyn/ofxAudioUnit

Place it in your addons folder

Create a new project using projectgenerator and include ofxAudioUnit

Open the project and add the audiounit.framework and coreaudiokit.framework

Now your project should run without errors

**<u>Step 2: Playing a file</u>**

_at the top of your .h file add:_

#include "ofxAudioUnit.h

_inside your testApp class add:_

ofxAudioUnitFilePlayer player;

ofxAudioUnitOutput output;

_inside your .cpp file add:_

_in setup():_

player.setFile(ofToDataPath(mySoundFile.mp3));

player.connectTo(output);

output.start();

player.play();

Now running your project will play your chosen file!!! Now, go ahead and erase iTunes!

_coming soon: adding effects to the DSP chain..._

try `auval -a` in terminal to see what audio units you have to work with

*   all of these arguments are 4 characters! if its 3, like aumu dls appl, make sure you append a space to the dls argument so its `'aumu' 'dls ' 'appl'

background info: 

*   [](http://en.wikipedia.org/wiki/Audio_Units)http://en.wikipedia.org/wiki/Audio_Units
*   [](https://developer.apple.com/library/mac/documentation/MusicAudio/Conceptual/AudioUnitProgrammingGuide/Introduction/Introduction.html)https://developer.apple.com/library/mac/documentation/MusicAudio/Conceptual/AudioUnitProgrammingGuide/Introduction/Introduction.html