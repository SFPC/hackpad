# Circuits #4  

In this class we will cover following concepts by building tiny drum machine. Please sign up to the Basic or Deluxe class session. Note Deluxe class may continue on Friday morning and continue over two weeks while I'm away. I am ordering special parts for those who want to make breadboard drum machine and synthesizers. Maybe we can form an** ALL LOGIC **band to perform at our final event. 

1.  CLOCK: Ring oscillator 
2.  INPUT: Potentiometer and light sensor 
3.  OUTPUT: Speaker and op amp/ quick introduction  
4.  Sine Wave
5.  Counter, MUX, Shift register: Let's put our memory for good use:

**Sign up **

Thursday 

Lab 1 1~3 pm Basic: 

(review of oscillation + 1 to 3)  max 7 students  

Simona

Claire

Jesse

Jon

Rachel

Motoi

Moises

Lab 2 3:30 ~ 6:30 pm Deluxe 

(1 to 3 and extra information on Sine wave generation and more logic to make awesome drum machine. this session may continue on Friday 11 am)  max 8 students 

-CLOSED-xd

 Paul

 Le

 Ishac

 Mini

 Andy

 Jonathan

**Introduction**

Last week, some of you were beginning to create feedback loop between oscillators and half adder. The circuit was adding: calculating Sum and Carry Out on it's own. Wow, that's technically an Automation. It's beginning to act more like a Computer now! By using logic gates in addition to oscillation, you were able to create alternative pulses. You are beginning to 'program' with circuits! It's exciting to see data travelling from one part of circuit to the other. 

This week, we will go ahead with SOUND due to popular demand and because this circuit can be used for your projects easily. In a nut shell, you will create a circuit that can amplify digital/analog signal to audible range. This circuit can be used in embedded system for your project, to power up small sound to a large one. 

 The SR Latch, D Flip Flop and other stuff regarding MEMORY becomes very important once again we start working with more complex logic: sequential logic for Counters, Registers and Multiplexers.  

**CLOCK **

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381868604465_undefined)

Tick tock... clock is the most important thing about computing with electronics. Last week, we made a simple and crude Relaxation Oscillator with Schmitt Trigger Inverter. 

By the way, what was Relaxation oscillator? You made it last week. [Check out the pad.  ](https://sfpc.hackpad.com/Circuits-3-iPLXtUZ5EP2)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381937328438_undefined)

 "... store energy in a [capacitor](http://en.wikipedia.org/wiki/Capacitor) and then dissipate that energy repeatedly to set up the oscillations. For example, the capacitor can be charged toward a positive power supply until it reaches a threshold voltage sufficiently close to the supply. At that instant, the capacitor can be quickly discharged (e.g., [shorted](http://en.wikipedia.org/wiki/Electrical_short))."... so it is "an [oscillator](http://en.wikipedia.org/wiki/Electronic_oscillator) based upon the behavior of a physical system's return to equilibrium after being disturbed"

Look at this animation for help.[](http://www.falstad.com/circuit/e-schmitt.html)http://www.falstad.com/circuit/e-schmitt.html 

The TTL 7414 chip has six NOT gate, which means you can make six independent oscillators. That's cool, because you can easily make different clocks for your drum machine. However, let's see if there is a better way to oscillate. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381936970138_undefined)

Now, lets downloand this spec sheet once again and try to read it. 

[](http://www.mcmelectronics.com/content/ProductData/Sp)[http://www.mcmelectronics.com/content/ProductData/Sp](http://www.mcmelectronics.com/content/ProductData/Spec%20Sheets/NTE7414.pdf)[ ](http://www.mcmelectronics.com/content/ProductData/Spec%20Sheets/NTE7414.pdf)[ec%20Sheets/NTE7414.pdf](http://www.mcmelectronics.com/content/ProductData/Spec%20Sheets/NTE7414.pdf)

[Ring Oscillator](http://en.wikipedia.org/wiki/Ring_oscillator) is really cool in many ways. 

1.  Odd number of inverters are chained to create FEEDBACK.  It's not based on Schmitt Trigger, so it can work in Hex Inverters without Schmitt Trigger. 
2.  "The stages of the ring oscillator are often differential stages, that are more immune to external disturbances." (from wiki page): This allows for more efficient and independent oscillation compared to Relaxation Oscillator. 
3.  You can have a clock that outputs opposite value synchronously. This can be very helpful introduction to parallel outpus. When controlling more complex logic with Memory, you will want to have parallel output of serial input. [(More on this ](http://www.allaboutcircuits.com/vol_4/chpt_12/6.html)when we talk about Counters and Registers) 
4.  You can control the oscillation with logic.  ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381938727253_undefined)

To make this oscillate in frequencies which human can percieve, You need to put a resistor between first Input and last Output, and capacitor between inverters. Remember I explained this slide in the second lecture? Ring oscillator works based on the principle of [propogation delay](http://en.wikipedia.org/wiki/Gate_delay#Electronics) and the fact that no physical device can switch instantenously. The delay in each gates plays in favor for us because, when chained in odd number, they can create desired frequency of oscillation. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381937457535_undefined)

Output is 1 when we connect the circuit. Through resistor, it charges the capacitor which is connected to the output of second Inverter. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381937817243_undefined)

And when the current has reached threshold of Capacitor, it discharges to the output of second Inverter, thus making last Inverter 1 input and 0 putput. Thus it's sending Negative signal (ground/ or Zero) to the capacitor and Input of first oscillator. (Look there's something wrong with the illustration above. On the far left, we have 0 and 1 in the same line. Yes, this diagram only makes sense with time-sensitive description.) Quickly after Capacitor is discharged, Input of last Inverter (which is connected to Output of Second Inverter) will become 0 again, making it's output 1, thus chargning that capacitor again. 

First, try to make it on your own and you can check the circuit simulation on the bottom. 

We have created a circuit which can control frequency via gate delay! Hooray, this is not using the characteristics of Schmitt Trigger! 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381937711997_undefined)

Put in more three dimensional perspective, these gates are dancing around each other, creating rhythm of feedback. The beautiful illustration is taken from[ this page.](http://en.wikibooks.org/wiki/Clock_and_Data_Recovery/Structures_and_types_of_CDRs/The_CDR'_VCO)  

Also check out this cool educational toy which you can use logic blocks to make Ring oscillator and all other basic logic blocks. [](https://www.sparkfun.com/tutorials/371)https://www.sparkfun.com/tutorials/371 

 OK>>>>> That was cool. this is a good time to get a firm grip on the concepts of Frequency, Wavelenght and Amplitude. Here is a short and sweet [explanation](http://www.studyphysics.ca/newnotes/20/unit03_mechanicalwaves/chp141516_waves/lesson44.htm).

It's not too late to check the data sheet to see what's happening inside the chip. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381941031041_undefined)

wait : these acronyms: Propagation delay time (Tphl/Tplh), Rise/Fall Time(Tr/T) . The unit is ns, which means nanosecond. that's very little amount of time! [](http://en.wikipedia.org/wiki/Nanosecond)[http://en.wikipedia.org/wiki/Nanosecond](http://en.wikipedia.org/wiki/Nanosecond) That is why we need resistor and capacitor to slow things down. 

Let's make seperate ring oscillator on your breadboard 

 ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381951031428_undefined)

 1. This very first step will chain First, Second and Third Inverter.

 ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381951126753_undefined)

 2. This 1K resistor will connect output of Third Inverter to input of first Inverter. Yes, it's chained. If you have an access to oscilloscope, you can look at very small and noisy oscillation happening due to feedback. 

 ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381953048957_undefined)

To delay the oscillation a bit, let's put capacitors between the inverters. Notice oscillation wouldn't occur if the cathode of capacitor (-) is placed at even number of inverters from anode (+). However, if the capacitor is simply flipped, anode in the first input of Inverter and cathode in the final inverter's input, it will oscillate because Ring oscillator charges capacitor and it discharves in to the first Inverter. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381953755369_undefined) 

Let's see this oscillate with our own eyes. 

Let's see it inverting in real life action by connecting LED output to two space between inverters. 

  ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1382043095603_undefined)

  If you connect osilloscope at the anode of capacitor, you can see the capacitor charning and discharning 

 The first one will have 100 uF cap + 1 k resistor (one you see it is oscillating, connect 1K potentiometer between Head and Tail of the chained Not gates. This will generate frequency of 3.2 HZ or so. Period is 311 ms and vMax is 3.6v (according to oscciloscope test under 5V input) 

1.  Let's put 10 uf in the place of 100uF, naturally, it has Frequency of 30~24 Hz at Period of 28~32 ms. 
2.  Lets put 1nf in the cap's place, now the Frequency is around 50 Hz with Period of 20 ms. The light looks like its lit up, but might not be producing visibile oscillation. Let's put LDR between the Ring and see if light input changes the frequency of oscillation. 

Now that we tested Ring oscillator works, Let's put variable resistors. Potentiometer and LDR. First one will have 100 uF and 1K Pot. The second one will have 1nF cap + LDR (Light sensor). this will make a very high pitch, itchy and scratchy sound.    

*Calculating frequency of Ring oscillation gets a big hairy compared to simple calculation of relaxation oscillator. Here are good introduction for ring oscillation, note these apply to CMOS and not necessairly TTL. 

[](http://nopr.niscair.res.in/bitstream/123456789/7244/1/IJPAP%2048(2)%20136-145.pdf)http://nopr.niscair.res.in/bitstream/123456789/7244/1/IJPAP%2048(2)%20136-145.pdf 

[](http://ijeee.iust.ac.ir/files/site1/user_files_5e3495/ijeee-A-10-3-78-dc358e0.pdf)http://ijeee.iust.ac.ir/files/site1/user_files_5e3495/ijeee-A-10-3-78-dc358e0.pdf 

[](https://ece.uwaterloo.ca/~cdr/pubs/docking_thesis.pdf)https://ece.uwaterloo.ca/~cdr/pubs/docking_thesis.pdf

[](http://www.fairchildsemi.com/an/AN/AN-118.pdf)http://www.fairchildsemi.com/an/AN/AN-118.pdf 

If you already are familiar with INPUT with variable resistance, make some of them and please skip ahead to OUTPUT. 

**INPUT**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381947368003_undefined)

We will be using 1K potentiometer, but the architeture is same as the 10K pictured above. Potentiometers have three terminals, middle one being the output with variable resisntance in accordance with position of wiper (knob). 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381947854055_undefined)

A potentiometer is a manually adjustable variable resistor with 3 terminals. Two terminals are connected to both ends of a resistive element, and the third terminal connects to a sliding contact, called a wiper, moving over the resistive element. The position of the wiper determines the output voltage of the potentiometer. 

Read more [](http://www.resistorguide.com/potentiometer/)[http://www.resistorguide.com/potentiometer/](http://www.resistorguide.com/potentiometer/)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381947841085_undefined)

Pots and other sensors 

[](http://en.wikipedia.org/wiki/Photoresistor)http://en.wikipedia.org/wiki/Photoresistor

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381948399415_undefined)

Oh. someone asked how LDRs work. 

It's resistivity decreases when light's intensity increases. It's behavior is due to photoconductivity. It's resistance increases if light's intensity decreases. Thus we have a variable resistor that reacts to the environment. LDRs are great to communicate wirelessly, in controlled environment within limited distance. Such application may become useful when working within various voltages and currents for installation or etc. 

Now we will solder Switches, Pots and Speakers! Soldering tips 

(Alternative to keyboards: switches, DIY and hacking 

Very basic introduction to circuit bending) 

**OUTPUT **

Speakers: What makes speaker to produce sound? Pressure!  

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381976551410_undefined)

"When an electrical signal is applied to the [voice coil](http://en.wikipedia.org/wiki/Voice_coil), [magnetic field](http://en.wikipedia.org/wiki/Magnetic_field) is created by the electric [current](http://en.wikipedia.org/wiki/Current_(electricity)) in the voice coil, making it a variable electromagnet. The coil and the driver's magnetic system interact, generating a mechanical force that causes the coil (and thus, the attached cone) to move back and forth, thereby reproducing sound under the control of the applied electrical signal coming from the [amplifie](http://en.wikipedia.org/wiki/Audio_power_amplifier)r" (from wiki) 

Here is the Cheap and dirty way: transistor speaker driver 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381976682313_undefined)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381976692592_undefined)

The same circuit drawn with resistor value and speaker position.

Notice that speaker is connected to the 5V and Collector of Transistor. In real world circuit, this can be made facing up, thus speakers will be set on the left side. ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1382044549924_undefined)

Now try jumping one oscillation to the other one. 

AND LET's start PARTY!!!! 

Try connecting NAND logic into this primitive drum machine. see if you can compose Logic which plays itself via feedback. 

Another cool challenge (or proposition as we like to say) is to think of a wave form. Draw it out, and try to make it with the logic gates. 

Some point soon, it will become very difficult to amplify complex signals, especially if you connect multiple signals into the transistor, it will just not be able to keep up with 

**OP AMP **

smarter way to amplify

Let's use LM 386. This is what is inside of the Amp. Bunch of transistors and resistors and diodes. Notice there are PNP resistor in combination with NPN. You can make these with discrete components if you want. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381984338024_undefined)

Let's make the amp with minimum parts. Can you try to make this circuit just by looking at the following diagram? 

 ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381984735067_undefined)

Now  It must be making some noise. Something you can hear, but it probably sounds pretty much like ants signing. 

Let's make this louder!!! 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381984840113_undefined)

the only difference between first amp and this one is that it has 10 uF capacitor between first and last pin. This works as Gain Control, bypassing internal resistance which makes it grow from gain of 20 (default) up to 200.

Let's read what's happening. [](http://www.ti.com/lit/ds/symlink/lm386.pdf)http://www.ti.com/lit/ds/symlink/lm386.pdf 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1382012105981_undefined)

How does this work?

LM 386 is one kind of op amp that is designed specifically for audio amplification. It has two special quality, Gain control and Bypass. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1382029258280_undefined)

ahh hackpad doesn't let you animate. 

check this page. Here is the easiest explanation I've encountered so far. [](http://www.talkingelectronics.com/projects/OP-AMP/OP-AMP-1.html)[http://www.talkingelectronics.com/projects/OP-AMP/OP-AMP-1.html](http://www.talkingelectronics.com/projects/OP-AMP/OP-AMP-1.html) 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1382029349615_undefined)

there was missing resistor between input and ground. Practically, it reduced noise, but not so noticable in small speaker 

+++++++++++++++++++++++++++++++  

[](http://hackaweek.com/hacks/?p=131)http://hackaweek.com/hacks/?p=131 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381983151445_undefined)

Chips we have (or will use)

LM 324 Quad [](http://www.ti.com/lit/ds/symlink/lm124-n.pdf)[http://www.ti.com/lit/ds/symlink/lm124-n.pdf](http://www.ti.com/lit/ds/symlink/lm124-n.pdf) *7 (getting today) 

LM 386N-1 Low Voltage Power Amp [](http://www.ti.com/lit/ds/symlink/lm386.pdf)[http://www.ti.com/lit/ds/symlink/lm386.pdf](http://www.ti.com/lit/ds/symlink/lm386.pdf) *6

LM 358N Low Power Amp [](http://www.ti.com/lit/ds/symlink/lm158-n.pdf)[http://www.ti.com/lit/ds/symlink/lm158-n.pdf](http://www.ti.com/lit/ds/symlink/lm158-n.pdf) *2

HA17358 Dual Op Amp [data sheet](http://javascript:openreq%28%27http//pdf.datasheetcatalog.com/datasheet/HitachiSemiconductor/mXqyszx.pdf')) *5

LM 301 [](http://www.utm.edu/staff/leeb/LM301.pdf)[http://www.utm.edu/staff/leeb/LM301.pdf](http://www.utm.edu/staff/leeb/LM301.pdf) *3 

LM 318 Single op amp *6 (Jon Wohl's box) [](http://www.ti.com/lit/ds/snosbs8c/snosbs8c.pdf)[http://www.ti.com/lit/ds/snosbs8c/snosbs8c.pdf](http://www.ti.com/lit/ds/snosbs8c/snosbs8c.pdf) 

Examples of Nic Collins' instruments Drum Machine 

[](http://milkcrate.com.au/_other/sea-moss/)[http://milkcrate.com.au/_other/sea-moss/](http://milkcrate.com.au/_other/sea-moss/) 

[](http://soundation.blogspot.com/2012/08/lm324-sine-wave-oscillator.html)[http://soundation.blogspot.com/2012/08/lm324-sine-wave-oscillator.html](http://soundation.blogspot.com/2012/08/lm324-sine-wave-oscillator.html)

[](http://www.sentex.ca/~mec1995/tutorial/xtor/xtor7/xtor7.html)[http://www.sentex.ca/~mec1995/tutorial/xtor/xtor7/xtor7.html](http://www.sentex.ca/~mec1995/tutorial/xtor/xtor7/xtor7.html)

**Sine Wave **

"Making sine wave with electronics is one of the highlight of learning about circuitry. It involves many layers of concepts that don't really make sense until you spend time thinking about WHY and HOW. We will be following the chapter of this book to create sine wave. 

[](http://www.ti.com/lit/ml/sloa087/sloa087.pdf)http://www.ti.com/lit/ml/sloa087/sloa087.pdf  " 

More information

TI paper [](http://www.ti.com/sc/docs/apps/msp/journal/aug2000/aug_07.pdf)http://www.ti.com/sc/docs/apps/msp/journal/aug2000/aug_07.pdf 

Sine wave oscillator  [](http://www.calvin.edu/~pribeiro/courses/engr332/Handouts/oscillators.pdf)http://www.calvin.edu/~pribeiro/courses/engr332/Handouts/oscillators.pdf 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381866249328_undefined)

Wien bridge 

[](http://sound.westhost.com/project22.htm)http://sound.westhost.com/project22.htm 

Parts to consider 

[](http://www.radioshack.com/product/index.jsp?productId=2062592)http://www.radioshack.com/product/index.jsp?productId=2062592

good reference 

[](http://jeelabs.org/2012/05/18/generating-a-sine-wave/)http://jeelabs.org/2012/05/18/generating-a-sine-wave/

    ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381866792786_undefined)                                

    ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381898580190_undefined)               

*   The heart of the Wien-bridge oscillator is its frequency-selective feed- back network. The op amp’s output is fed back to the inputs in phase. Part of the feedback is positive (makes its way through the frequency- selective _RC _branch to the noninverting terminal), while the other part is negative (is sent through the resistor branch to the inverting input of the op amp). At a particular frequency _f_0 = 1/(2π_RC_)_, _the inverting input volt- age (_V_4) and the noninverting input voltage (_V_2) will be equal and in phase—the positive feedback will cancel the negative feedback, and the circuit will oscillate. At any other frequency, _V_2 will be too small to can- cel _V_4, and the circuit will not oscillate. In this circuit, the gain must be set to +3 V (_R_1 and _R_2 set the gain). Anything less than this value will cause oscillations to cease; anything more will cause the output to satu- rate. With the component values listed in the figure, this oscillator can cover a frequency range of 1 to 5 kHz. The frequency can be adjusted by means of a two-ganged variable-capacitor unit.                                                                                         - from Practical Electronics book 
*     

**More Logic **

SR LATCH

Flip flop

D Type

Counters

Shift registers 

Multiplexers 

We are moving bits !!! 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zJbsDvclB0T_p.77239_1381869110014_undefined)

YEAHHHH 