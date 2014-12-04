# Circuits #3 

Sign up 

**10 am**

7 people max 

Simona 

Mini

Ishac

Andy

Paul

Jonathan

**1pm **

8 people max 

rachel

le

motoi

Jazon

Jon

By end of last week's lab, you made all kind of logic gate with NAND gates. Thank you for your patience and encouragements. 2

Some notable comments and suggestion from students:

*   Can there be a better way of learning Logic gates other than mechanically copying circuit simulation? Is it possible to make a learning scenario where students are working from Truth Table to circuit on student's own? 
*   Are there ways of learning Logic without having to make tiny circuits? It may be more difficult to some than others. 
*   What is the purpose of learning binary logic beyond the very basics, when higher level language are already operating within CPU? 
*   How is the evolution of computer hardware related to computer programming language we use now? 

This week, I would like to show binary arithmetics using logic gates. 

1.  Make a Full Adder with two NAND chips and one pair of transistors.
2.  Make a Half Subtractor with two NAND chips. 
3.  Schmitt Trigger Oscillator: Ring Oscillator and Relaxation oscillator  

Also, something we skipped over are in

*   Soldering lessons
*   Parts organizing tips 

Let's download LOGISIM software, it's a cool logic simulation tool kit. [](http://ozark.hendrix.edu/~burch/logisim/)http://ozark.hendrix.edu/~burch/logisim/ 

We will be using that as well as circuit simulation tool, (ah. only if these two combined!)

[](http://fritzing.org/download/)http://fritzing.org/download/ 

**Addition **

Let's make Half Adder with logic gates! 

We will need XOR and AND(Do you mean AND?). 

Try to work out a way that you can construct this from NAND logic gates.  

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_iPLXtUZ5EP2_p.77239_1381191033622_undefined)

This can be built with seven NAND gates; four to make XOR and three to make AND.

Behavior of the circuit should be when A and B are 1 and it's the time to carry over a bit to the next digit, XOR switches off and AND turns 1. 

Here is one way of making it. I bet it will be easier, and more accurate to figure out on your own, than making it from this simulation. 

First, you are most likely to have working XOR or XNOR on your breadboard from last week. Let's keep that in place and make new AND gate. Key is to jump signal from A and B  (the switches) straight into AND gate. You can do that by connecting long wire from switch into it, or connect one of the XOR gate's pin. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_iPLXtUZ5EP2_p.77239_1381503467769_undefined)

Full Adder with XORs, ANDS and OR

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_iPLXtUZ5EP2_p.77239_1381193189063_undefined)

Full adder will need total of 15 NAND gates to construct it. Wow. that's alot of NANDs. 

Is there a way to make it with less gates if you have 6 inverters?

Tip: other than using 2 NAND to make AND, you can connect output of NAND to inverter to get AND, and for OR, you can connect two of the AND outputs into NAND to get OR output.

There are many Adder I.C.s available. The reason for using NAND gates to Add is to prove binary calculation follows fundamental logic for its operation, thus it can be manipulated logically.  

**CLOCK**

Introducing HEX INVERTERS! 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_iPLXtUZ5EP2_p.77239_1381464164212_undefined)

This is what Hex Inverters do inside of the box. 

It gives opposite value of input. 

That's basic inverter, a bunch of NOT gates. 

Now, let's look at Schmitt Trigger NOT gate and what we can do with it. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_iPLXtUZ5EP2_p.77239_1381464313475_undefined)

Now this is Schmitt Trigger Hex Inverter. I explained what ST is on the second lecture. It allows oscillation when you create feedback loop between Y and A with resistor and place capacitor between A and ground. What happens is that Y (let's say it's 1) connected to A via resistor, slowly charging the capacitor. While it's charging, A becomes 1 state, due to Y's current flowing into it. Since A is 1, Y becomes 0 state, thus not flowing current into A. Soon, the capacitor will discharge and A becomes 0. The filling and unfilling cycle begins, and It clocks! 

 Note Capacitor is 100 uF and resistor between A and Y is 1K. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_iPLXtUZ5EP2_p.77239_1381494488635_undefined)

**Subtraction **

(Lecture note) : Explain how binary subtraction works  

1.  Append leading zero if necessary 
2.  Apply Two's complement (make zero into one, and vice versa) and add one to the  
3.  Add the complemented numbers 
4.  Remove Most Significant Bit 

The complex (or more just confusing) way two's complement works toward subtracting binary numbers [](http://www.wikihow.com/Subtract-Binary-Numbers)http://www.wikihow.com/Subtract-Binary-Numbers 

Question: Is there a way to make Half Subtractor using NAND gates only? 

Answer: Half Subtractor with XOR and AND with an inverted input. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_iPLXtUZ5EP2_p.77239_1381493743450_undefined)

Oh. it's a good time to make use of that inverter! Note AND should stay as AND, except we invert A input before feeding into the AND gate. Here is one possible way of connecting them but please try your own design.  (the first one I uploaded for morning Lab is wrong)

 ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_iPLXtUZ5EP2_p.77239_1381504959107_undefined)

Now, let's start to make circuits to remember. 

**Latches **

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_iPLXtUZ5EP2_p.77239_1381491676678_undefined)

Following is the truth table you want to get from this latch. 

Note it's SR with Active Low, notice the bar on S and R. It means it sets the latch at Low or 0.  

Truth table for SR latch
<table style="font-size:13px;cell-spacing: 0px; border-collapse: collapse;"><tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">S</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">R</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">Q</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">Q bar</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added"></td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">INV</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">INV</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">Race condition</td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added"></td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added"></td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added"></td>
</tr>
<tr><td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">0</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added">1</td>
<td style="border:1px solid #999; min-width: 50px;height: 22px;line-height: 16px;padding: 0 4px 0 4px;" class="added"></td>
</tr>
</table>

from wikipedia 

SR NAND latch 

This is an alternate model of the simple SR latch which is built with [NAND](http://en.wikipedia.org/wiki/NAND_gate) [logic gates](http://en.wikipedia.org/wiki/Logic_gate). _Set_ and _reset_ now become active low signals, denoted S and R respectively. Otherwise, operation is identical to that of the SR latch. Historically, SR-latches have been predominant despite the notational inconvenience of [active-low](http://en.wikipedia.org/wiki/Logic_level) inputs.

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_iPLXtUZ5EP2_p.77239_1381494983423_undefined)

Here is one way of making it, but please try to create the latch on your own way first. It is often more confusing and difficult to work from simulations.

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_iPLXtUZ5EP2_p.77239_1381494911373_undefined)

**Flip Flop **

D type Flip Flop

Practical Use: 

1.  Stop Go sign 
2.  Divide by Two Counter [](http://www.doctronics.co.uk/4013.htm)http://www.doctronics.co.uk/4013.htm 

**From lectures**

The Badlands between ALU and C 

Instruction Sets 

Assembly Language 

C 

[](https://scs.senecac.on.ca/~ipc144/pages/content/expre_p.html#ari)https://scs.senecac.on.ca/~ipc144/pages/content/expre_p.html#ari

ALU 

[](http://www.philadelphia.edu.jo/academics/qhamarsheh/uploads/Lecture_4_Arithmetic_and_logi_%20Unit_and_Assembly_Language%20.pdf)http://www.philadelphia.edu.jo/academics/qhamarsheh/uploads/Lecture_4_Arithmetic_and_logi_%20Unit_and_Assembly_Language%20.pdf

DEEDS 

[](http://www.esng.dibe.unige.it/deeds/Index.htm)http://www.esng.dibe.unige.it/deeds/Index.htm

[](http://mxp.physics.umn.edu/f06/Lecture/CLec1.pdf)http://mxp.physics.umn.edu/f06/Lecture/CLec1.pdf

VHDL 

[](http://esd.cs.ucr.edu/labs/tutorial/)http://esd.cs.ucr.edu/labs/tutorial/

[](http://www.seas.upenn.edu/~ese171/vhdl/vhdl_primer.html)http://www.seas.upenn.edu/~ese171/vhdl/vhdl_primer.html

[](http://classes.soe.ucsc.edu/cmpe225/Fall01/synver.pdf)http://classes.soe.ucsc.edu/cmpe225/Fall01/synver.pdf 

**NOTES FROM CLASS**