# Arduino Beyond Newbie Class

**Short review from class 1 (5 min)**

*   TBD
*   Questions from class one?

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_9RyFb9XmDbK_p.251586_1418087703411_undefined)

*   Be sure to check the examples to see if your library came with examples:
*   ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_9RyFb9XmDbK_p.251586_1418087827323_undefined)
**   Get some libraries:
*   [](http://arduino.cc/en/Reference/Libraries)http://arduino.cc/en/Reference/Libraries

*   No special characters in library names!!!

*   What a standard library includes (keypad below):

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_9RyFb9XmDbK_p.251586_1418088079061_Screenshot 2014-12-08 20.21.00.png)

It can be helpful to look at the keywords file:

*   ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_9RyFb9XmDbK_p.251586_1418088186363_Screenshot 2014-12-08 20.22.23.png)
*

**Storing a value in EEPROM (10 min)**

*   EEPROM = Electronically Erasable Programmable Read Only Memory
*   Ram is zeroed when power is removed from the microcontroller.  EEPROM is the only way to record variables without an external SD card.
*   EEPROM addresses are 8 bits (0-255).

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_9RyFb9XmDbK_p.251586_1418088540950_AVR_memory_01_lrg.jpg)

Example code ( a device that does something different each time it's restarted:

*

[](https://gist.github.com/extrasleepy/187225991a36bfa95cd9#file-gistfile1-txt)https://gist.github.com/extrasleepy/187225991a36bfa95cd9#file-gistfile1-txt

Similar example: does a different thing each time you turn it on: [](https://vimeo.com/89358523)https://vimeo.com/89358523

<u>Storing numbers larger than a byte in EEPROM:</u>

Example: a device that changes based on how many times it has been reset/unplugged:

(requires LED on pin 12)

*

[](https://gist.github.com/extrasleepy/72aee868899c6ae3493d)https://gist.github.com/extrasleepy/72aee868899c6ae3493d

**AVR Direct Port Manipulation (5 min)**

Control many pins with less code.  Get close to the metal!

Ports:

*   B (digital pin 8 to 13)
*   C (analog input pins)
*   D (digital pins 0 to 7)

*   DDR(port) = B00000000 //sets port as input or output
*   PORTD = B00000000 //sets all pins low

*

[](https://gist.github.com/extrasleepy/9ad7c6439b7b1b93b59b)https://gist.github.com/extrasleepy/9ad7c6439b7b1b93b59b

more here:

[](http://www.arduino.cc/en/Reference/PortManipulation)http://www.arduino.cc/en/Reference/PortManipulation

**Making Arduino random( ) = MORE random! (5 min)**

[](http://arduino.cc/en/Reference/Random)[http://arduino.cc/en/Reference/Random](http://arduino.cc/en/Reference/Random)

[](http://arduino.cc/en/Reference/RandomSeed)http://arduino.cc/en/Reference/RandomSeed

randomSeed(analogRead(0));    //use this as a seed value.  Reads analog value on pin that has nothing actually hooked to analog pin.  This is also known as a floating input.

*

[](https://gist.github.com/extrasleepy/3cd2872c4359601850c8)https://gist.github.com/extrasleepy/3cd2872c4359601850c8

**Hardware Interrupts and Sleep ( 5 min)**

<u>What are they good for?</u> = A button that can be pressed at any time in the program!

*   Uno Interrupts are on Digital 2 (Interrupt 0) and Digital 3 (Interrupt 1)
*   Interrupt can detect LOW, RISING, FALLING, CHANGE, HIGH
*   AttachInterrupt(interrupt address, function, detection constant); 
*   ISR (interrupt service routines) cannot pass variables 
*   Interrupts wake Arduino from sleep.

BUILD: Add button to from Digital Pin 2 to GND.

CODE:

*

**Sleeping:**

The Arduino has a handful of sleeping functions that it understands by invoking commands specific to the atmel chip. To use sleep functions, we _usually_ need to include these three header files:

*   #include <avr/sleep.h>
*   #include <avr/power.h>
*   #include <avr/wdt.h>

These allow us to use power saving modes like:

*        *     SLEEP_MODE_IDLE         -the least power savings
*        *     SLEEP_MODE_ADC
*        *     SLEEP_MODE_PWR_SAVE
*        *     SLEEP_MODE_STANDBY
*        *     SLEEP_MODE_PWR_DOWN     -the most power savings

Each of these modes allows different circuitry (timers, oscillators) to go to 'sleep' and help save power.  There are two ways an Atmel Chip can be awoken from a sleep, by a special kind of timer, or by a signal using our friend the interrupt.  

For waking with a timer there's a separate clock on the chip, called a _watchdog timer_, which periodically wakes the MCU back up. Watchdog timers typically have an 8 sec maximum wait before they "bite" or check for an interrupt but can be as quick as 30 ms.  

There are other libraries that simplify low power commands, enerlib is one example.  A new favorite is Narcoleptic!  

Download the library here:  

[](https://code.google.com/p/narcoleptic/downloads/detail?name=Narcoleptic_v1a.zip)https://code.google.com/p/narcoleptic/downloads/detail?name=Narcoleptic_v1a.zip

Here's a simple example:  

*   {
*   #include <Narcoleptic.h>
**   void setup() {
*     pinMode(2,INPUT);        // set pin 2 as input 
*     digitalWrite(2,HIGH);   //  pull it high initially 
*     pinMode(13,OUTPUT);     //  make 13 an output 
*     digitalWrite(13,LOW);   //  initially set it low 
*   }
**   void loop() {
*     int a;
**     // Merlin the cat is snoozing... Connect digital pin 2 to ground to wake him up.
*     Narcoleptic.delay(500); // During this time power consumption is minimised
**     while (digitalRead(2) == LOW) {
*       // Wake up CPU. Unfortunately, Merlin does not like waking up.
**       // Swipe claws left
*       digitalWrite(13,HIGH);
*       delay(50);
*       
*       // Swipe claws right
*       digitalWrite(13,LOW);
*       delay(50);
*     }
*

Here's another example using an interrupt and the avr library instead.  

*       

[](https://gist.github.com/extrasleepy/e120be94dccda907a206)https://gist.github.com/extrasleepy/e120be94dccda907a206

**Talk with Processing or OF. (15 min)**

<u>First, communicate without Firmata!!!</u>

use Serial.write( );

Code on Arduino:

*

[](https://gist.github.com/extrasleepy/c2807755b6276da6bdac)https://gist.github.com/extrasleepy/c2807755b6276da6bdac

Processing Code:

*

[](https://gist.github.com/extrasleepy/3269fc604e0bde755128)https://gist.github.com/extrasleepy/3269fc604e0bde755128

*   //Processing function to print serial ports
*   println(Serial.list());
**   //Listing the available serial ports with a for loop!!
*   for (int i = 0; i < Arduino.list().length; i++) {
*       println(i + " --> " + Arduino.list()[i]);
*     }

<u>Going the other way:</u>

Upload 'Standard Firmata' to the UNO:

Examples -> Firmata -> Standard Firmata 

In processing install the Arduino library here-> 

[](http://playground.arduino.cc/Interfacing/Processing)http://playground.arduino.cc/Interfacing/Processing

Then run the 'Arduino Output' skectch in: 

Processing->Examples->Contributed Libraries->Arduino Output

<u>Super Simple Arduino/OF sketch using Firmata:</u>

[](https://www.dropbox.com/s/43i9jk5koglxd65/arduinoControl.zip?dl=0)https://www.dropbox.com/s/43i9jk5koglxd65/arduinoControl.zip?dl=0

**I2C other modules (20 min)  **

<u>I2C = synchronous, bus (devices can be chained to one "master" device)</u>

*   2-wire communication standard
*   SDA = (Serial Data) OR Analog 4
*   SCL = (Serial Clock) OR Analog 5
*   Use "Wire" library for I2C.

![](http://www.best-microcontroller-projects.com/images/i2c-tutorial-typical-signals.png)

*   1. Send the START bit (S).
*   2. Send the slave address (ADDR).
*   3. Send the Read(R)-1 / Write(W)-0 bit.
*   4. Wait for/Send an acknowledge bit (A).
*   5. Send/Receive the data byte (8 bits) (DATA).
*   6. Expect/Send acknowledge bit (A).
*   7. Send the STOP bit (P).

<u>Since the devices are addressable, you can have many devices on one bus!!!!</u>

![](http://embedded-lab.com/blog/wp-content/uploads/2011/05/MutipleI2C_Devices.png)

[](http://embedded-lab.com/blog/wp-content/uploads/2011/05/MutipleI2C_Devices.png)http://embedded-lab.com/blog/wp-content/uploads/2011/05/MutipleI2C_Devices.png

<u>Exercise: Have two Arduinos talk to each other!!!</u>

Build this:

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_9RyFb9XmDbK_p.251586_1418265089249_i2c.PNG)

<u>Code for Transmitting Arduino:</u>

*

[](https://gist.github.com/extrasleepy/f82e11d15073228f42ef)https://gist.github.com/extrasleepy/f82e11d15073228f42ef

<u>Code for Receiving Arduino:</u>

*

[](https://gist.github.com/extrasleepy/580d8e8e2708a4b00478)https://gist.github.com/extrasleepy/580d8e8e2708a4b00478

<u>More on I2C</u>

I2C: [](http://www.arduino.cc/en/Reference/Wire)http://www.arduino.cc/en/Reference/Wire

More about Synchronous and Asynchonous communication.

[](https://learn.sparkfun.com/tutorials/serial-communication)[https://learn.sparkfun.com/tutorials/serial-communication](https://learn.sparkfun.com/tutorials/serial-communication)

Time Permitting: Try these I2C ready devices: Neopixels, Digit-display, LED Matrix, Accelerometer.

[Zachary Dunham](/ep/profile/okfl7kqsZvK)

**Short Lecture -Nothing Hands on: Different Arduino devices.  Which one is for me? Breadboarding an Arduino / ATtiny (10 min)**

[Uno](http://arduino.cc/en/Main/arduinoBoardUno) (most popular - tons of examples)

[Leonardo](https://Leonardo) (good for serial control easily acts as keyboard or mouse)

[Due](http://arduino.cc/en/Main/ArduinoBoardDue) (54 I/O pins, 3.3v only, more powerful CPU, faster, bigger, more storage

[Yun](http://arduino.cc/en/Main/ArduinoBoardYun) (wifi / ethernet built in $75+, long startup time)

[Arduino Ethernet](http://arduino.cc/en/Main/ArduinoBoardEthernet) (Cheaper/Faster way to connect to Internet, PoE powered by Ethernet)*

[Arduino Pro](https://www.sparkfun.com/products/10915) (Cheap,  Almost same footprint as UNO, $15 without requiring building)*

[Arduino Pro Mini](https://www.sparkfun.com/products/11113) (Cheap, $10, smallest footprint)*

[LilyPad Arduino](https://www.sparkfun.com/products/9266) (Designed for wearables)*

[Teensy](https://www.pjrc.com/teensy/) (super small, 32bit, powerful, inexpensive and powerful for Audio)

Easy tool for bootloading a raw ATMEGA:

[](http://shop.evilmadscientist.com/productsmenu/tinykitlist/253)http://shop.evilmadscientist.com/productsmenu/tinykitlist/253

RAW ATMEGA*

[](http://www.digikey.com/product-detail/en/ATMEGA328P-PU/ATMEGA328P-PU-ND/1914589)http://www.digikey.com/product-detail/en/ATMEGA328P-PU/ATMEGA328P-PU-ND/1914589

PRE-BOOTLOADED ATMEGA*

[](https://www.sparkfun.com/products/10524)https://www.sparkfun.com/products/10524

Breadboard Arduino*

[](http://arduino.cc/en/Main/Standalone)http://arduino.cc/en/Main/Standalone

Breadboard ATtiny

[](https://www.sparkfun.com/products/11801)https://www.sparkfun.com/products/11801

[](https://www.sparkfun.com/products/9378)https://www.sparkfun.com/products/9378

[](https://learn.sparkfun.com/tutorials/tiny-avr-programmer-hookup-guide/?_ga=1.117748937.1776796729.1410905664)https://learn.sparkfun.com/tutorials/tiny-avr-programmer-hookup-guide/?_ga=1.117748937.1776796729.1410905664

*Requires FTDI cable to program: [This](https://www.sparkfun.com/products/9716) or [This](https://www.sparkfun.com/products/9718)

**Short Lecture -Nothing Hands on: Tried and True Sensors and Add ons**

**Multiplexing (10 min)**

Multiplexing!  

-Allows us to control many digital states without using an equal number of digital pins on the Arduino. With a common chip like the 74HC595 16 leds can be controlled by using only 3 digital pins on the arduino.  

-Achieved by quickly scanning across each intersection of the 'rows and columns' hundreds of times a second the multiplexer is able to uniquely control each intersection or led in this example.  

A nice instructable [here](http://www.instructables.com/id/Multiplexing-with-Arduino-and-the-74HC595/)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_9RyFb9XmDbK_p.251746_1418275199670_FMMWU6BH2TJ4FPQ.LARGE.gif)

Ultrasonic (distance): [](https://www.sparkfun.com/products/8501)https://www.sparkfun.com/products/8501

Infrared (distance): [](https://www.sparkfun.com/products/242)[https://www.sparkfun.com/products/242](https://www.sparkfun.com/products/242)

Wide angle motion: [](https://www.adafruit.com/products/189)https://www.adafruit.com/products/189

Basic wifi: [](https://www.adafruit.com/products/1469)https://www.adafruit.com/products/1469

tilt/acceleration: [](https://www.adafruit.com/products/2019)https://www.adafruit.com/products/2019

SMS: [](https://www.adafruit.com/products/1963)https://www.adafruit.com/products/1963

Radio Control: 

[](https://www.adafruit.com/products/128)https://www.adafruit.com/products/128

[](https://www.adafruit.com/products/126)https://www.adafruit.com/products/126

Serial Lcd: [](https://www.sparkfun.com/products/9394)https://www.sparkfun.com/products/9394

Parallel lcd: [](https://www.sparkfun.com/products/255)https://www.sparkfun.com/products/255

Triggering samples: [](https://www.sparkfun.com/products/10628)https://www.sparkfun.com/products/10628

or  [](https://www.sparkfun.com/products/12646)https://www.sparkfun.com/products/12646[ ](https://www.sparkfun.com/products/12646https://www.sparkfun.com/products/12767)with [](https://www.sparkfun.com/products/12767)https://www.sparkfun.com/products/12767 

Stepper motor control: [](https://www.sparkfun.com/products/11876)https://www.sparkfun.com/products/11876

Control many servos: [](https://www.adafruit.com/products/815)https://www.adafruit.com/products/815

Adding Outputs / multiplexing (shift register): [](https://www.sparkfun.com/products/10680)https://www.sparkfun.com/products/10680

Digit Display:

[](https://www.adafruit.com/products/880)https://www.adafruit.com/products/880

LED Matrix:

[](https://www.adafruit.com/products/902)https://www.adafruit.com/products/902

Barometric Pressure:

[](https://www.adafruit.com/product/992)https://www.adafruit.com/product/992

Pressure (force):

[](https://www.sparkfun.com/products/8712)https://www.sparkfun.com/products/8712

RFID:

[](https://www.sparkfun.com/products/11827)https://www.sparkfun.com/products/[11827](https://www.sparkfun.com/products/retired/8419)

with:

[](https://www.sparkfun.com/products/13030)https://www.sparkfun.com/products/13030

Pulse:

[](https://www.sparkfun.com/products/11574)https://www.sparkfun.com/products/11574

Audio Detection:

[](https://www.adafruit.com/products/1713)https://www.adafruit.com/products/1713

Capacitive Touch:

[](https://www.sparkfun.com/products/12017)https://www.sparkfun.com/products/12017

Small Joystick:

[](https://www.adafruit.com/products/512)https://www.adafruit.com/products/512