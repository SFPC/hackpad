# Arduino Newbie Class

Facilitated by Zach Dunham and [Andrew Kleindolph](/ep/profile/Fff9BhWVGtc)

**Preparations:  **

*   Bring Arduino if you have one.  Be willing to work with partner if not enough devices.
*   Download and <u>confirm</u> operation of Arduino 1.0.6 software.
*   Zach and Andrew: Gather breadboards, wire, strippers, LEDs/RGBLeds, buttons, 10K resistors, variable resistors, servos, TIP 120s, diodes, DC motors

**What is it? (5 min)**

*   Arduino is a single chip computer on a single micro-controller board.
*   Atmel Microcontroller (Uno= AVR atmega 328) with bootloader. 
*   Without bootloader a special icsp (in-circuit serial programmer) is needed.  
*   Bootloader takes 2k of space takes 1-3sec to start up.  
*   Separate ATmega controller deals with serial communication. (Except on Leonardo and a few other boards which operate on only one microcontroller).  

Uno Board:

![](http://arduino.cc/en/uploads/Main/ArduinoUno_R3_Front.jpg)

[](http://arduino.cc/en/uploads/Main/ArduinoUno_R3_Front.jpg)http://arduino.cc/en/uploads/Main/ArduinoUno_R3_Front.jpg

<u>Components  and Pin Breakout:</u>

![](http://pcomp2013.aisencc.com/wp-content/uploads/sites/2/2013/09/ARDUINO_V2.png)

[](http://pcomp2013.aisencc.com/wp-content/uploads/sites/2/2013/09/ARDUINO_V2.png)http://pcomp2013.aisencc.com/wp-content/uploads/sites/2/2013/09/ARDUINO_V2.png

<u>How is it different from other small computers?</u>

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Q2FrBtpZBVA_p.251586_1417812366908_Screenshot 2014-12-05 15.45.16.png)

Comparison Article:

[](http://makezine.com/2013/04/15/arduino-uno-vs-beaglebone-vs-raspberry-pi/)http://makezine.com/2013/04/15/arduino-uno-vs-beaglebone-vs-raspberry-pi/

<u>Power:</u>

*   Input Voltage on Jack: between 6 and 20v (7-12v recommended) 
*   5v regulated- digital standard. 
*   3.3v regulated - Lower energy consumption.  Good for lower voltage / small battery projects
*   Mixing 5v and 3.3v can be tricky.
*   Arduino uses 5mA-25mA current on its own.  4 AA pack (6v) will power approx. 60hr (assuming 1500mAH/25mA AA)

<u>Programming IDE : Language based C/C++</u>

*   More C than C++  (C yields smaller code to fix 32k flash storage).  
*   Language is here: [](http://arduino.cc/en/Reference/HomePage)http://arduino.cc/en/Reference/HomePage

Great PDF by colleague Natalie Freed: [](http://sites.lwhs.org/techarts/files/2013/10/arduino-cheat-sheet-1-2.pdf)http://sites.lwhs.org/techarts/files/2013/10/arduino-cheat-sheet-1-2.pdf

<u>Don't ignore the learning power of the example files!!!!</u>

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Q2FrBtpZBVA_p.251586_1417819681691_Screenshot 2014-12-05 17.47.47.png)

<u>Basic Sketch Structure: </u>

At the top (optional):

*   **includes**
*   **defines**
*   **global variables**

**setup( ){**

What do you want the hardware to do?;

**}**

 **loop ( ) {**

 Your program.  Repeats as long as device runs (duh?);

** }**

** myCustomFunction( ) {**

 optional;

** } **

**Tabs :** can be used to organize functions.

**Exercise 1: Flash Onboard LED (10 min)**

Code: 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Q2FrBtpZBVA_p.251586_1418048923446_undefined)

_>>>>>Important: _Declaring PINS as input or output in setup. 

_____________________________________________________  

void setup() {                

  // initialize the digital pin as an output.

  pinMode(13, OUTPUT);     

}

 _____________________________________________________                                                         

digitalWrite sets pin HIGH or LOW

<u>Challenges:</u>

*   1.  We can use two other alternatives to HIGH and LOW.  What are they?
*   2. Port the external LED to another pin and change the rate of flash.
*   3. What's the fastest you can flash an external LED and still see the flashing?  (try changing delay to a float variable to get super precise).
*   4. What if we want the light to flash two times when the microcontroller starts up when we turn it on and then never again until restart?  What's the easiest solution with no extra commands?

<u>Advice:  </u>

Blink is always the first program to run on a new Arduino or an Arduino that you are unsure of its health.  Built in LEDs can vary.  You can always blink the TX LED (usually PIN 1) if you are not sending data back to the host computer.

*

**Exercise 2: Serial output for debugging. (5 min)**

_Important: _Declaring baud rate

[](http://arduino.cc/en/Serial/begin)http://arduino.cc/en/Serial/begin

<u>Output data types:</u>

[](http://arduino.cc/en/Serial/Print)http://arduino.cc/en/Serial/Print

(paste example code from above page to see data types in serial window)

<u>println vs. print</u>

println includes carriage return!

CODE: 

____________________________________________________

void setup() {

  // initialize serial communication at 9600 bits per second:

  Serial.begin(9600);

}

void loop() {

  Serial.print("I've been running for ");

   Serial.print(millis()); 

   Serial.println(" mS");

}

_____________________________________________________

Challenges:

*   1.  Print the state of an LED
*   2. Print runtime in millis, seconds, minutes, hours

**Exercise 3: control external LED with PWM pulse-duration modulation). (10 min)**

<u>Analog vs Digital </u>

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Q2FrBtpZBVA_p.251586_1418051699703_analog_digital.jpg) 

<u>Emphasize: what is PWM (pulse width modulation)</u>

[](http://arduino.cc/en/Tutorial/PWM)http://arduino.cc/en/Tutorial/PWM

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Q2FrBtpZBVA_p.251586_1418051721541_pwm.gif)

Build This:

![](http://arduino.cc/en/uploads/Tutorial/simplefade_pin9_schem.png)

[](http://arduino.cc/en/uploads/Tutorial/simplefade_pin9_schem.png)http://arduino.cc/en/uploads/Tutorial/simplefade_pin9_schem.png

CODE:

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Q2FrBtpZBVA_p.251586_1418051813606_undefined)

<u>Can you PWM all Arduino pins?  No!!!</u>

You need to see the  **~**  next to a pin

<u>But actually YES:</u>

use softPWM library!

[](https://code.google.com/p/rogue-code/wiki/SoftPWMLibraryDocumentation)https://code.google.com/p/rogue-code/wiki/SoftPWMLibraryDocumentation

<u>Challenges:</u>

*   1. Change fade speed
*   2. Fade one LED on as the other fades off
*   3. Fade between colors on RGBled

**Exercise 4:  Digital Input with push button.  (15 min)**

<u>Build this:</u>

[](http://arduino.cc/en/Tutorial/DigitalReadSerial)http://arduino.cc/en/Tutorial/DigitalReadSerial

CODE:

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Q2FrBtpZBVA_p.251586_1418052478102_undefined)

_<u>Important: </u>_<u>Declaring PINS as input in setup. </u>

_____________________________________________________  

**void setup() {        **        

  // initialize the digital pin as an input.

   pinMode(pushButton, INPUT);    

**}**

 _____________________________________________________        

<u>Emphasize: pull-up, pull-down resistors</u>

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Q2FrBtpZBVA_p.251586_1418052675810_undefined)

<u>Emphasize: Debouncing Switches + Giving user time to press / let go.</u>

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Q2FrBtpZBVA_p.251586_1418052854182_undefined)

<u>Using INPUT_PULLUP.</u>

[](http://arduino.cc/en/Tutorial/InputPullupSerial)http://arduino.cc/en/Tutorial/InputPullupSerial

**Exercise 5: Analog input (Photoresistor / Potentiometer) (15 min)**

<u>Build this:</u>

Potentiometer Schematic:

![](http://arduino.cc/en/uploads/Tutorial/AnalogReadSerial_sch.png)

Now with a Photoresistor:

but wait....Voltage Dividers!

Because the photoresistor is a variable resistor with two leads instead of three like the potentiometer, we need to add it as part of a voltage divider.  

What's a voltage divider?  

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Q2FrBtpZBVA_p.251746_1418227058245_voltage_divider.jpg)

Photoresistor Schematic:

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Q2FrBtpZBVA_p.251746_1418226827139_photoresist.png)

[](http://arduino.cc/en/uploads/Tutorial/AnalogReadSerial_sch.png)http://arduino.cc/en/uploads/Tutorial/AnalogReadSerial_sch.png

<u>Analog to Digital Conversion:</u>

Use analog pins A0 - A5

Continuos voltage becomes numbers between 0 to 1023

<u>Challenge:</u>

*   Control an 8-bit tone with photo-resistor and map( ) command
*   [](http://arduino.cc/en/Tutorial/Tone2)http://arduino.cc/en/Tutorial/Tone2

**Exercise 6: Control DC. motor with external MOSFET. (15 min)**

Important: Current limitations of Microcontroller pins : 200mA!  DC motor requires more!

<u>Use MOSFET ( The metal–oxide–semiconductor field-effect transistor) </u>

![](https://alonsodub.files.wordpress.com/2012/07/tip120.png)

[](https://alonsodub.files.wordpress.com/2012/07/tip120.png)https://alonsodub.files.wordpress.com/2012/07/tip120.png

<u>Role of diode.</u>

![](http://upload.wikimedia.org/wikipedia/commons/8/83/Diode_pinout_en_fr.svg)

[](http://upload.wikimedia.org/wikipedia/commons/8/83/Diode_pinout_en_fr.svg)http://upload.wikimedia.org/wikipedia/commons/8/83/Diode_pinout_en_fr.svg

*   Block counter EMF from motor (electro motive force)
*   [](http://en.wikipedia.org/wiki/Counter-electromotive_force)http://en.wikipedia.org/wiki/Counter-electromotive_force

<u>What to Build:</u>

[](http://bildr.org/?s=tip+120)[http://bildr.org/?s=tip+120](http://bildr.org/?s=tip+120)

<u>CODE:</u>

Just use the blink sketch!!!

**Exercise 7: Servo Control (15 min)**

How does a servo work:

![](https://www.servocity.com/assets/images/Servo_Breakdown.jpg)

[](https://www.servocity.com/assets/images/Servo_Breakdown.jpg)https://www.servocity.com/assets/images/Servo_Breakdown.jpg

![](http://bansky.net/blog_stuff/images/servo_pulse_width.png)

[](http://bansky.net/blog_stuff/images/servo_pulse_width.png)http://bansky.net/blog_stuff/images/servo_pulse_width.png

What to Build:

[](http://arduino.cc/en/Tutorial/Sweep)http://arduino.cc/en/Tutorial/Sweep

CODE:

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Q2FrBtpZBVA_p.251586_1418054379667_undefined)

<u>Challenge:</u>

*   1. Control movement of servo with buttons
*   2. Control direction of servo with potentiometer or photo-resistor
*   3. Use two photo-resistors and two servos to build a robot that seeks darkness (or light if you are so optimistic).

**Epilog: A few tips for troubleshooting:**

*     Test individual components before creating a complex system.
*     Do not leave a circuit on while building or when it doesn’t do what you expect.
*     Frequent Serial.print( ) commands during testing but comment out if possible on finished project.
*   Check hardware and software.  Is it plugged in?
*   Use a multimeter, continuity tests, voltage tests.  