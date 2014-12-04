# Servo Workshop with OF and Arduino with Caitlin 

Use firmata to communicate between arduino and openframeworks

[](http://firmata.org/wiki/V2.3ProtocolDetails)http://firmata.org/wiki/V2.3ProtocolDetails

The baud rate for firmata and OF is 57600

*   setup arduino is called as an argument of the setup arduino function

Check that you are addressing the right port on your computer and update frameworks.

GO TO TERMINAL AND TYPE IN ls /dev/tty.*

    //FIND THE USB NUMBER AND UPDATE THE FUNCTION SO THAT YOU ARE ADDRESSING THE RIGHT PORT

Any time we address a pin in OF, we use a slightly different syntaxt than in processing

*   We must refer to the ardunio object
*   eg. having 
*    ard.sendDigitalPinMode(2,ARD_INPUT);

Predefined constants to address pins are

sendDigitalPinMode(2, ARD_INPUT);

sendAnalogPinRepoting(0,ARD_ANALOG);

also ARD_OUTPUT and ARD_PWM - we need to define the pin mode for firmata

SERVOS

*   to attach servos we call ard.sendServoAttach(9);
*   We can only use pins D3, D5, D6, etc.

Firmata is more robust than the serial communication. It handles data better. This is an advantage of using OF rather than using Processing which relies wholly on serial communications.  (actually, processing does have a fimata library -- see [](http://firmata.org/wiki/Download))http://firmata.org/wiki/Download)

Firmata is better then serial for complex messages, since it's sometimes really painful to send multi-byte or variable length messages from one platform to another.  they operate at different speeds and serial is very low level.  With firmata, you can quickly change your host code without changing your arduino code = faster dev times.   it's like OSC vs networking code.  

Check voltage on Servos when buying

Pin 9 common for Servos

90% have 180 degree rotation

(DC motors have 360, continuously rotating but less easy to tell where to move)