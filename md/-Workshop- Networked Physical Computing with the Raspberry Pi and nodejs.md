*   [Workshop] Networked Physical Computing with the Raspberry Pi and nodejs

We are going to make a website, that talks to a server, on a raspberry pi, that controls a traffic light! This will be a hands-on workshop, like Taeyoon's labs, with 4 people per lab. All you need is a laptop.

*   Paul
*   Le
*   Jesse
*   Claire
*   Jason
*   Rachel
*   Motoi
*   Tega

**<u>Workshop Times</u>**

Pick a time that works for you:

**Oct 23 (Wednesday), 2pm-6pm (conflicts with intro to arduino)**

*   [motoishmz](/ep/profile/w4lbIML7ANO)
*   [Moises Sanabria](/ep/profile/v6pSS8EP8fM)
*   Le
*   Jesse
*   Rachel

**Oct 28 (Monday), 1pm-3pm (reschedule cuz jonathan is sick)**

*   Claire
*   Paul
*   Jason
*   [Jonathan Wohl](https://sfpc.hackpad.com/ep/profile/rdI4x5fVNUz)
*   Tega
*   (Ishac) I'll sit and listen :)

*   Sorry I had to reschedule cuz I am sick today :(

Topics

Here are topics that may be covered, depending on what people are most interested in we can skip or delve deeper in any one area

*   the raspberry pi hardware
*   linux and the commandline
*   creating a webserver with node.js
*   building a http and websocket api
*   digital output (and pwm for fake analog output)

Materials Provided

*   Raspberry Pi
*   screen
*   sd card
*   tiny keyboard/mouse

Questions/Suggestions

  Add any questions / suggestions here so I know what people are most interested in.

NOTES

Raspberry Pi setup:*[](https://gist.github.com/jkosoy/5379904)https://gist.github.com/jkosoy/5379904

Mount your Raspberry Pi as a hard drive:

[](http://www.openframeworks.cc/setup/raspberrypi/Raspberry-Pi-SMB.html)http://www.openframeworks.cc/setup/raspberrypi/Raspberry-Pi-SMB.html

RPi Remote Access:

[](http://elinux.org/RPi_Remote_Access#Running_a_remote_CLI)http://elinux.org/RPi_Remote_Access#Running_a_remote_CLI

*   To connect to Pi from your computer:

*   Finder > Command+K > _smp://192.blah_...

*   To use the terminal in your computer:

*   _ssh pi@192.168.1.203_
*

*   _/home/pi/Desktop_

*   at any time from any folder will get there, because the slash at the beginning. without slash is from your working directory.

*   _pwd_ give your full paths you're in.
*   _cat_ hello.js will read all the content inside hello.js
*   _ps ax_ to check the running processes
*   kill 'number' to kill the process
*   kill -9 'number' to really kill it. zas!

  [](http://eirikb.github.io/nipster)http://eirikb.github.io/nipster

[](https://github.com/jedahan/traffactlight/blob/master/traffactlight.coffee)https://github.com/jedahan/traffactlight/blob/master/traffactlight.coffee