# Transistor 101 

First of all, connect power and ground of each end of breadboard. Assuming it's powered with 5V battery, let's begin building simple logic gates with discrete components. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413660685975_undefined)

We will need to supply power and ground, two signals into the switch.

Notice that the power (red) and ground (blue) are connected by one vertical space between them. That is where COM, or signal will come out. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413660771883_undefined)

We will use tiny black switch that looks like this .

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413660809667_undefined)

electrical symbol is this 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413660824071_undefined)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413661166611_undefined)you will notice that the switch is tiny bit bulky, taking extra horizontal lines on top and bottom. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413661418622_undefined)

Let's try connecting a LED to this switch. We will place 100k resistor through the middle of switch, output or COM. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413662462544_undefined)

You can stretch the leg to ground for quick test. You will notice the LED is not turning on. It's because due to the 100k resistor, current is reduced to the point where there is not enough voltage for LED to be emitting light. 

To get to the nuts and bolts of LED, let's look at it's [spec sheet. ](http://www.jameco.com/Jameco/Products/ProdDS/333973.pdf)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413663758730_undefined)

It says typical voltage is 1.8V. Typical LED needs at least 1.8~ 2 V to operate, while specific characteristics vary for different colors and types, sizes and etc. 

The condition is set If=20mA. that means if about 20mA of current is supplied to the LED. mA means miliamps.  

*   mA = milli amps = 10^-3 which means that there are 1000 in 1 amp 
*   uA = micro amps = 10^-6 which means that there are 1000000 in 1 amp 

You'll need to learn how to use multimeter sometime soon. Let's skip it for now, I can demonstrate it to those who are curious. Some [links.](https://learn.sparkfun.com/tutorials/how-to-use-a-multimeter/measuring-current)

With multimeter we can measure current of going through 1K resistor is 5 mA and if we swap it to a smaller value resistor, for example  390ohm (Orange White Brown), our current will be 12 mmA. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413664784367_undefined)

Now, we should be using smaller value resistor for this LED. The only reason we are using 1K is that I'm keeping the parts pretty simple for now, and to avoid any more confusions. 

If we use 250ohm resistor, we might have an ideal current for this led, leaving us at 20mA as current. Get this color stripes for resistors!  

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413664938888_undefined) 

What if we supply less than that 2V? thus lower current?  it's visibly dimmer.  It's not easy to say what is the lowest voltage it operates, because it's subjective to how bright rest of the space is. If you lit an LED in completely dark room, you will see it with very little voltage. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413663982384_undefined)

so.. around 10aM, intensity will be around 40. 

more on Ohm's law sometime soon.

Now we know we don't have enough current to turn on the resistor. Let's use Transistor to do so!  

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413661514523_undefined)

Place NPN transistor on the other side of breadboard. Notice middle leg of transistor is connected to COM. Switch will command the transistor, opening and closing the current flow through collector to emitter. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413661860814_undefined)

![](/static/img/pixel.gif)

Now connect LED through Red (5V) and 1 k resistor(Brown, Black, Red stripe) to collector of the transistor. 

And connect Emitter of transistor (bottom leg) to Blue(ground) 

It's okay to have resistor connected directly to Red and cathode of LED (shorter leg) connect to Collector of Transistor.

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413661966613_undefined)

It will end up looking like the image above. I had additional wire for ease of viewing. The circuit is the same, and doesn't matter if resistor comes before or after LED in this case. 

so what's happening? 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413662044738_undefined)

when the switch is off, current from 5V stops at the collector of Transistor. It doesn't have anywhere to go, because the transistor is closed due to [depletion.](http://en.wikipedia.org/wiki/Depletion_region)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413662176402_undefined)

when the switch is connected to Red (5V), it sends signal to the transistor to open up. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413665486216_undefined)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413665969128_undefined)

voila! 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413666127751_undefined)

current goes through the led and transistor and lights up.

Small current is used to switch on larger current going through the resistor and LED. 

Alternatively you can try another design called "Emitter follower switch.

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413667654434_undefined)

This switch pulls current from the collector and emits to the LED. Notice I'm using 470 ohm resistor, because it will be brighter.

This alternate design tells us that transistor can be used to design various switching characteristics. It is useful to note it's two variations as we think about making logic gates with transistors. 

More information 

[](http://hyperphysics.phy-astr.gsu.edu/hbase/electronic/transwitch.html)http://hyperphysics.phy-astr.gsu.edu/hbase/electronic/transwitch.html

and very helpful guide in fundamentals of transistors. 

[](http://hyperphysics.phy-astr.gsu.edu/hbase/solids/trans2.html#c1)http://hyperphysics.phy-astr.gsu.edu/hbase/solids/trans2.html#c1 

**NOT gate**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413668409895_undefined)

Now you can create not gate with transistor! 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413668442621_undefined)

R1 will be 1K and R2 is 100k. A is our switch. Vcc is power. A with over bar is our output, LED connected to ground. Q1 is the NPN transistor. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413668734077_undefined)

explanation 

"The operation of this circuit is simple. The input is connected through resistor R2 to the transistor’s base. When no voltage is present on the input, the transistor turns off. When the transistor is off, no current flows through the collector-emitter path. Thus, current from the supply voltage (V<sub>cc</sub> in the schematic) flows through resistor R1 to the output. In this way, the circuit’s output is HIGH when its input is LOW.

When voltage is present at the input, the transistor turns on, allowing current to flow through the collector-emitter circuit directly to ground. This ground path creates a shortcut that bypasses the output, which causes the output to go LOW.

In this way, the output is HIGH when the input is LOW and LOW when the input is HIGH." [](http://www.dummies.com/how-to/content/electronics-projects-how-to-create-a-transistor-no.html)http://www.dummies.com/how-to/content/electronics-projects-how-to-create-a-transistor-no.html 

**AND gate**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413666111054_undefined)

now connect two transistors to make AND gates! 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413668117193_undefined)

On the schematic I drew on the whiteboard, it looked like this. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413669094791_undefined)

Jonas asked why there needs to be a resistor between emitter of second (bottom) transistor, because it works fine without it. And he's right. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413669237456_undefined)

It will work without the resistor connecting transistor. However, it's advisable to have the resistor  because it will matter in later, when we combine more transistors to create other logic. 

Next, Finish all other logics on your own!

*    clues are on the white board! 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413668592769_undefined)

Following schematics are taken from t[his site.](http://hyperphysics.phy-astr.gsu.edu/hbase/electronic/trangate.html) It's what I based on for our class. Simply replace 4.7K with 1K and 10K with 100K for our homework. 

**NAND gate**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413670062218_undefined)

**OR Gate**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413670053674_undefined)

**NOR Gate**

I realize NOR gate I drew on the whiteboard has a mistake. It needs a resistor between + power and the first Resistor's collector. It would've looked like this 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413670038741_undefined)

An easier way of making it would be like this... 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pHMijwpmTAu_p.77239_1413669980925_undefined)

References

Cheat sheets [](http://hyperphysics.phy-astr.gsu.edu/hbase/electronic/trangate.html)http://hyperphysics.phy-astr.gsu.edu/hbase/electronic/trangate.html 

check out [](http://phillipstearns.wordpress.com/pcb/)http://phillipstearns.wordpress.com/pcb/