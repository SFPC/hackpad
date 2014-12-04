# Lab 2 

Goal: Manipulate TTL QUAD NAND gates to make All possible binary logic gates including XOR 

Concepts: Functional completeness of NAND 

Let's be friends with NAND CAT today!!!! 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380643546593_undefined)

[OHHH YEAHHH](http://www.youtube.com/watch?v=QH2-TGUlwu4) 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_daAp1gyCF9r_p.77239_1380635756427_undefined)

**Working with breadboard: **

Ground (either Blue or Red) needs to be connected with ground of battery. Voltage (4.5~5V) needs to be connected to red line. Both sides of breadboard needs to be connected with jumper wire. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380636344497_Screen Shot 2013-10-01 at 10.05.28 AM.png)

This shows three AAA batteries but, of course it can be three AA batteries or 9V battery with voltage regulator.

Let's start by building Not gates and make record of it by writing truth table and taking picture (or video)

Before we move on, let's look at the spec sheet for 7400. you can find them by searching TTL 7400 online. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380636793627_Screen Shot 2013-10-01 at 10.12.23 AM.png)

Remember when I was explaining Boolean logic for NAND, I wrote 

A | B | Y

0 | 0 | 1 

0 | 1 | 1 

1 | 0 | 1 

1 | 1 | 0 
<table style="font-size:13px;cell-spacing: 0px; border-collapse: collapse;"><tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">A</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">B</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">Y</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
</tr>
</table>

(Im trying to make tables with hackpad.. it's a bit weird and makes extra column everytime the boxes are filled. ) 

now you see that we have four NAND in one chip, thus the name Quad Nand makes sense.

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380637626432_Screen Shot 2013-10-01 at 10.26.08 AM.png)

This image is taken from TTL cook book, which I recommend you keep close to your working area because sometimes it is easier to look through the book than search for spec sheet each time. 

Note that we have four gates in the chip. How cool! Make sure to note pin outs, starting from #1, there are Nand gates with outputs at #3, #6, #8 and #11. 

First step, connect Pin #7 to ground and #14 to voltage. you don't need to use red and blue cable, although i prefer to do so Just make sure you are not connecting ground to voltage. what would be worse is to connect #7 to voltage and #14 to ground. Reversing them will likely to damage this chip. 

*    ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380636568411_Screen%20Shot%202013-10-01%20at%2010.09.08%20AM.png)

First step will be to check NAND works.

**SPDT **

Connect SPDT switch to ground and voltage. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380638807548_undefined)

SPDT stands for Single Pole Double Throw. It means COM switches between L1 and L2 according to the diagram above. Oh, by the way, these differences between switches are super important for our future investigation because SPST looks similar but only swtich on and off (closed and open circuit). Take a minute to look at all these options of switches.  [](http://en.wikipedia.org/wiki/Switch)http://en.wikipedia.org/wiki/Switch They also come in all kinds of cool shape, and also we can make them with paper and conductive material. 

 ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380639004157_Screen Shot 2013-10-01 at 10.49.57 AM.png)

Sfpc kit uses these mini switches. middle pin COM stands for Common. That provides signal from one to another state. 

1.  We have two of them connected on the breadboard. COM pin is connected to A1 and B1 of Nand gate. Let's call the left one A switch and the right one B switch. 
2.  Connect pin #3 which is Y of the first gate, to anode of LED, the longer leg. connect cathode of LED to 470 ohm resistor which connects to ground. If both switches are HIGH (or 0), the LED must turn off, thus LOW state (or 0). 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380638759383_Screen Shot 2013-10-01 at 10.45.24 AM.png)

If that works, take a picture of the gate with truth table and move on. Taking picture is for you to remember each gate and also to record how gates can be manipulated as[ combinational logic](http://en.wikipedia.org/wiki/Combinational_logic). 

These are gates which you can build with one Quad Nand Chip 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380635941598_undefined)

Allrite, everyone ready to twist some logic?

**NOT **

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380647833040_undefined)

Start making NOT gate by Connecting both inputs of gate together. You would do that by putting wire between 1A and 1B .

 ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380640526525_Screen Shot 2013-10-01 at 11.15.15 AM.png)

Notice orange wire between 1A and 1B. and thae right switch (which was connected to 1B) is now disconnected. We will need to do that because NOT gate is a single input inverter. If both switches are connected to the inputs and giving opposing signals, it will short out the circuit.  

If all are done, you should be getting 
<table style="font-size:13px;cell-spacing: 0px; border-collapse: collapse;"><tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">A</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">Y</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
</tr>
</table>

**AND**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380647858234_undefined)

Now let's make AND gate. as we saw on the drawing, you can do that by inverting NAND gate, which gets rid of Bubble infront of NAND, because it is double inversion.

 ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380641723344_Screen Shot 2013-10-01 at 11.35.07 AM.png)

You will connect B switch again to 1B. 1Y (which is outcome of the first NAND) is connected to 2A (which is pin #4) which is also connected to 2B (which is pin #5). Now it will return following values. Make sure you get lights on when both of switch is HIGH. 
<table style="font-size:13px;cell-spacing: 0px; border-collapse: collapse;"><tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">A</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">B</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">Y</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
</tr>
</table>

**OR** 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380647883991_undefined)

Now, let's make OR gate. Things are getting more busier now because to make two inverters 

 ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380642400547_Screen Shot 2013-10-01 at 11.46.21 AM.png)

Ohhha. First two gates are used as inverter which feed in to 3A and 3B of the third gate. It's 3Y output is connected to LED, thus giving OR value of following table.
<table style="font-size:13px;cell-spacing: 0px; border-collapse: collapse;"><tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">A</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">B</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">Y</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
</tr>
</table>

**NOR** 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380647913062_undefined)

NOR is using another inverter on the Y of OR gate. Once again, we are going to trick NAND to make NOT gate. I will not include simulation of the circuit, but simply give you logic diagram one more time.

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380642938458_undefined)

Let's try to make this on our own! It should be self explanatory by now! :) 

(*__*)V 

More complex gates are waiting for us. 

**XOR **

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380647990234_undefined)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380643687897_undefined) 

This is an XOR Gate which has a truth table like the following. 
<table style="font-size:13px;cell-spacing: 0px; border-collapse: collapse;"><tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">A</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">B</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">Y</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
</tr>
</table>

**XNOR **

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380643779267_undefined)

This is XNOR gate which can be achieved by adding an inverter (Not gate) in the Y of XOR gate. You need another IC or work with transistors. Ask for more chips, it's easier! 
<table style="font-size:13px;cell-spacing: 0px; border-collapse: collapse;"><tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">A</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">B</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">Y</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
</tr>
</table>

XNOR gate is very cool, but it's hardly used, where as XOR is instrumental in binary addition and so on. XNOR gate also needs additonal NAND gate made into Not gate. so, it can't be made with Quad NAND chip. You will need another NAND or Not (made with one transistor!) or Inverter chip. So, it's taking more foot prints on the precious real estate of your breadboard. 

**Teaser for next class **

Now, with all the logic gates we built, you can start to take advantage of its characteristics for binary calucation. 

Next week, we will start to make Adders and Subtractors. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380647255350_undefined)

This is what we want to make so we can add A and B and get sum of S and carry out to C incase A and B are HIGH. ** **

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380642736909_Screen%20Shot%202013-10-01%20at%2011.51.58%20AM.png)

 You can implement it by making NAND into XOR and making AND with two NPN transistors.

You might ask, 

Q: "why in the world should we be making XOR from NAND, when we have[ XOR chips ](http://www.cs.smith.edu/~thiebaut/270/datasheets/sn74ls86rev5.pdf)available for less than a dollar?" 

A: "it's so that we can to utilize logic values from different points ot XOR(made of NAND) to get various gates and minimize clutter in logic design"

Oh oh, we have been already taking advantage of [de Morgan's Law](http://en.wikipedia.org/wiki/De_Morgan's_laws) which basically states "principles that conjunction and disjunction, or union and intersection, are dual. Thus the negation of P & Q is equivalent to not-P or not-Q" according to online library. Will explain in next lecture.  

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380642736909_Screen Shot 2013-10-01 at 11.51.58 AM.png)

Note NPN transistors are put in series to turn Emitter on when both inputs are high. 

You can also use only NAND gates by making final NAND into AND by tying both inputs. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fmuY2tuqYVG_p.77239_1380637326626_undefined)