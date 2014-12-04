# Motors w/ Jacob

aka Motors for Artists

**Motor Theory**

Basic theory of magnets: opposite poles attract

"Magnets, how do they work?" Magic.

Electromagnets: As an experiment, a coil of insulated copper wire around an iron nail, with the wire attached to a power source, it will act like a magnet as long as power is flowing.

Solenoids are simple devices that use an electromagnet to push/pull a rod, creating a small amount of linear motion.

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_pIHR19CZawU_p.77281_1382625316618_undefined)

[](https://www.sparkfun.com/products/10391)https://www.sparkfun.com/products/10391

Ohm's law: The higher the voltage, the greater the current (more electricity) flows through the circuit

[](http://en.wikipedia.org/wiki/Ohm)http://en.wikipedia.org/wiki/Ohm's_law

By hooking up a bunch of electromagnets in sequence and switching them on and off in order, you can move a permanent magnet linearly.  If you set up the electromagnets in a ring, you make a permanent magnet spin... a motor.

A generator is the opposite of a motor — spinning the permanent magnet produces current in the coils.

Switching is called "Commutation" — how this happens is the biggest difference between the different types of motors.

Stator — stationary part

Rotor — the part that rotates

Brushed DC Motor

*   Regular DC motors use 'self-commutation,' meaning their position can not be controlled
*   They always want to move into the next position
*   They wear out due to the friction of the brushes touching the contacts
*   Controlling the voltage controls the speed
*   They tend to move really fast — in the thousands of RPMs

**Shopping for motors:**

[](http://www.robotshop.com/motors-actuators.html)http://www.robotshop.com/motors-actuators.html

[](http://www.andymark.com/)http://www.andymark.com/

[](http://allelectronics.com/)http://allelectronics.com/

[](http://www.servocity.com)http://www.servocity.com

[](http://www.pololu.com/)http://www.pololu.com/

**DC Motors **

*   Easy to control, just change the voltage
*   Can use Pulse Width Modulation with an Arduino to change the speed as well.

**Gear Motors**

*   Spur Gear Motors

        *   The shaft is off center from the gearing, sometimes these are cheaper but less balanced, and make more noise.

*   Planetary Gear Motors

        *   Little gears wrap around the main gear and the main shaft from the motor, so the output shaft is still lined up with the motor's shaft.
    *   Cost more but stronger and quieter.

**Servo Motors**

*   Knows its position with either a rotary encoder (which would let it rotate around and around as a continuous motor), or with a potentiometer (which would limit it to 180°)
*   Come in standard sizes
*   [](http://www.servocity.com/html/what_servo_do_you_need_.html)http://www.servocity.com/html/what_servo_do_you_need_.html

**Stepper Motors**

*   For controlling direction
*   Externally commutated
*   Ex: Printers
*   Attach encoder if you need feedback

**Linear Actuator**

*   Rotational motor with a gear that turns like a screw
*   Push and pull motion 
*   Ex: opening doors