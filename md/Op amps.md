# Op amps

This pad is for me to keep track of resources and designs for using and understanding op amps for amplification and signal generation. This stuff is really the dark alley of analog circuits, and things gets pretty complex very easily, unreadable, and not usable. I don't understand most of it other than some theory and practical use. so I will stick to few simple objectives which can be used by sfpc students projects right away. 

**Objectives **

1.  Amplify signal (for simple synth): Andy, Moises, Ishac, + 
2.  Amplify microphone input (contact and electret): Le, Andy + 
3.  Create Sawtooth, Triangle, and Sine waves: Andy, Moises, Ishac, +
4.  Motor control: Tega, + 

**Books**

Analog synthesizer : Ray Wilson

Chapter 5: The Incredible Op Amp

My copy is in sfpc. 

Practical Electronics for inventors 

[](http://www.andyholtin.com/links/Practical_Electronics_for_Inventors.pdf)http://www.andyholtin.com/links/Practical_Electronics_for_Inventors.pdf 

Chapter 7: 

Some books from Jim Williams 

[](http://www.introni.it/pdf/Williams%2007%20-%20Book%20Chapters.pdf)http://www.introni.it/pdf/Williams%2007%20-%20Book%20Chapters.pdf 

Op amp for everyone 

www.ti.com/lit/an/slod006b/slod006b.pdf

more theoretical

Cybernetics: Human use of human beings 

[](http://asounder.org/resources/weiner_humanuse.pdf)http://asounder.org/resources/weiner_humanuse.pdf 

Feedback 

**Chips **

Op amps we have at sfpc

*   741 * 2 
*   LM 301 AN * 3 
*   LM 324 * 2 
*   LM 386 * 4
*   LM 358 * 7 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384094138259_undefined)

**Sine wave**

silly intro video, but watch around 1 min for reminder 

*

[](http://youtu.be/aJAZHPqEUKU)http://youtu.be/aJAZHPqEUKU 

Important new concepts 

Phase: [](http://en.wikipedia.org/wiki/Phase_(waves))http://en.wikipedia.org/wiki/Phase_(waves) 

Reminder about sine waves

![](http://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/ComplexSinInATimeAxe.gif/400px-ComplexSinInATimeAxe.gif)

[](http://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/ComplexSinInATimeAxe.gif/400px-ComplexSinInATimeAxe.gif)http://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/ComplexSinInATimeAxe.gif/400px-ComplexSinInATimeAxe.gif

[](https://tutsplus.com/tutorial/understanding-simple-harmonic-motion-and-its-applications-in-games/)https://tutsplus.com/tutorial/understanding-simple-harmonic-motion-and-its-applications-in-games/ 

One page paper that will be your guiding light 

[](http://www.ti.com/lit/an/slyt164/slyt164.pdf)http://www.ti.com/lit/an/slyt164/slyt164.pdf 

Let'd download that pdf and save it on your computer.

Ordering parts is a daunting process that one never quiet get used to. 

So you go online, to sites like Digikey and search for parts. There are more than a dozen of almost identical parts. Here is the chip we'd like to use, because it's the same one as what is used in TI manual.  [](http://www.ti.com/lit/ds/symlink/tlv2470a.pdf)http://www.ti.com/lit/ds/symlink/tlv2470a.pdf 

I find a bunch and they share the same spec sheet, for different parts. It's time to find out what exactly is the part you are looking for. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384243480130_undefined)

now let's look closely. 2470 has one op amp. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384243407717_undefined)

2472 has two op amps. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384243543571_undefined)

2474 has four op amps. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384243575930_undefined)

They share the same characteristics, but are packaged differently. You can use whatever that fits your needs. Also, checking spec sheet carefully will let you build circuits interchangeably, not having to stick with the schematics provided. 

Scroll down and you will see supply voltage is limited to 7V. good to know. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384285424576_undefined)

**Phase Shift Oscillator **

PSO can be built from simple Transistor with RC components. 

video [](http://www.youtube.com/watch?v=T8lEGChW5jA)http://www.youtube.com/watch?v=T8lEGChW5jA 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384137725535_undefined)

This is what it looks like. As youtube video demonstrates, .1 uF for Capacitors, 680 ohm for R and 1m ohm for R1 (Feedback) and 2K for RL should work. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384114561169_undefined)

This is a design to use single op amp. The circuit uses Other designs show 1k for R and 100 K for feedback 

**Wien Bridge Oscillator **

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384114501597_undefined)

**Quadrature Oscillator **

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384098105125_undefined)

the same circuit can be explained in a simplified version here 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384113991898_undefined)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384297016747_undefined)

You can check this page for an animated illustration of how these two op amps are used to create sine wave. [](http://www.falstad.com/circuit/e-sine.html)http://www.falstad.com/circuit/e-sine.html 

This is a quadrature oscillator I built now following a schematic below with LM324. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384113775665_undefined)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384113895871_undefined)

what's happening here is " some equivalent circuit to clip the signal fed back from the Cosine output to the Sine integrator." according to this site [](http://www.play-hookey.com/oscillators/audio/quadrature_oscillator.html)http://www.play-hookey.com/oscillators/audio/quadrature_oscillator.html 

This design works pretty well. but I'd like to have slower frequency. So I brought some extra components from home. 

with lamp 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384096285013_undefined)

Wien bridge 

[](http://en.wikipedia.org/wiki/Wien_bridge_oscillator)http://en.wikipedia.org/wiki/Wien_bridge_oscillator 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384096235493_undefined)

one without a lamp 

**Motor **

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pUrFgJQucxm_p.77239_1384095410813_undefined)

 