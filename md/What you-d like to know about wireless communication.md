# What you'd like to know about wireless communication

wireless communication vocab-- not sure how to talk about this stuff!

Hello, Dan here. I'm doing some work with wifi, so maybe I can help with some of these questions. I'm also doing a wifi workshop at SFPC soon.

i wanna know how networks/servers communicate with wireless devices

what equipment is necessary to capture data--audio for example-- and to upload it, retrieve it, manipulate it and send it back out to a server and/or wireless device.

Capturing the data is kind of a separate process from the networking parts. I'd assume something like an Arduino would be the thing. Turning sound into data is the job of an ADC (analog to digital converter). Let's just assume you have the data in some standard format (like WAV samples) and you want to push it up to a server somewhere. (We'll also ignore data compression, but in a real scenario sending uncompressed audio data may be too high bandwidth.)

There are many ways to transmit data, but to get that data onto a server that can process it I would say HTTP is your best choice. HTTP is built on TCP/IP (so basically wifi) and is how the web handles data, both sending it to your browser and letting you upload stuff. The work I'm doing with small scale wifi is essentially the same process as what's happening on the Internet. Hand waving a little here, but we'd be doing the same thing that SoundCloud might use to accept your audio submission.

Each kind of web technology does this uploading process differently—I could tell you [how it works in PHP](http://us3.php.net/manual/en/features.file-upload.php)  for example—but the general idea is the same regardless. You're running some code on a computer that is listening for requests coming in from the network. If a request matches certain conditions, then the result is that the data being sent from the client (your Arduino with audio data) gets saved onto the server.

Manipulating audio data is another thing that depends a lot on how you want to manipulate it. There are some command-line tools like ffmpeg that can do some basic things, but if you want to get more creative, you'll probably need to dive into some low level waveform stuff. I don't know much about this, but I'm sure some noise musician types would be worth asking. (One guess is that using node.js to open up the binary data and fiddle with it could be a good starting point. Unfortunately node.js isn't supported by my weakling wifi routers, although you can run it on an RPi.)

Sending the data back to the wireless device is just like downloading anything else from a web server. Basically if you know the URL of the thing you want (like the audio we just fiddled with), then you request it with HTTP again. The hard part is knowing what the URL will be, and at what point it's safe to download. Like if the audio manipulation we did before takes some time to complete, how soon can we expect to download it? Depending on the application, you might just check in every N seconds, and see if it's finished, and if it is finished have some way to find out what the URL is. This type of code is dumb, and annoying to write, but that's how the web is built. Dumb and annoying code. It's getting better, for example using WebSockets could make this process faster and less kludgy, but my process is one of choosing the dumbest approach that kinda-sorta works and then deciding which parts are worth making smarter.

ok cool.... EVERYONE> DAN will teach Nov. 7th afternoon during Circuits class time!!!! 

what is going on in the situation of shoes with LED’s connected w/gps /maps and which light up green when you walk towards your destination and red when you walk away from it.

The easy part first: determining the color of the LED based on current lat/long is just a matter of calculating distance to some destination, and then tracking over time if the distance is increasing or decreasing.

Harder problem: knowing your current lat/long. A smartphone knows lat/long, and could potentially use that information to tell some shoes to turn this or that color, but writing code for smartphones can be tricky.

I have a p5 sketch that communicates via BT and it's pretty easy to get long / latitude.  I can probably whip something up.  there are also GPS chips for arduino but (a) they are pricy (b) they drain battery.    For the google shoe we use long / latitude on the phone and send to the shoe. 

The part that seems the hardest to me (because I tend not to work on projects like this): setting up communication between something small/light enough to live in a shoe and something smart enough to read GPS sensor data and calculate lat/long distances. That more sophisticated part would also need to be programmed with a destination, so there's an added user interface aspect to this. Getting back to the communication mechanism—XBee maybe, or Bluetooth?

bluetooth is good for phone communication since it's built in.  xbee is good device to device or device to computer. 

if i want to create a messaging tooth brush to send messages to my friend in brazil while he brushes his teeth how could i set it up-- i.e. which types of sensors and if i want to use a small thermal printer to print out my messages to him how does the thermal printer receive the data?

This sounds like a use case for the [BERG cloud](http://bergcloud.com/) Devkit thing (or maybe an XBee?). That kind of low-level sensor stuff isn't something I'm very experienced with, but I probably should get my hands on one of those Devkit devices. The reason this wouldn't work well with wifi is that setting up a connection to communicate over HTTP is too complex to fit inside something as small and passive as a toothbrush.

good examples of what kinds of magical things bluetooth is good for and when its not enough i.e. when do you have to find a more rebust means of wireless communication ?

Bluetooth is robust enough for transmitting mouse data or cell phone voice data, but I think the main difference is with transmission range. (I should caveat this by saying most of what I'm working on is limited to wifi, so I could be wrong about Bluetooth w.r.t. range.) My emphasis is usually not so much on "robustness" but "what will most people's existing devices support?" Basically I'm interested in what magical things are possible with a mobile web page mediating communication between people with smartphones. I know there are other magical things one can do wirelessly, but that's my bias.

also, energy requirements.  bluetooth and bluetooth LE are designed around specific energy needs and have different classes (class 1, class 2, etc) that specify range.

how much backend/server side stuff does one need to know to get even small things up and running?

Making flat files available via HTTP is the smallest/simplest possible thing you could start to get up and running. The limitation is that it's read-only, so it's kind of limited to broadcast scenarios. I can start by showing how that works in my workshop, and then what the next step would be to do stuff like accept user submitted data.

differences between devices-- such as XBee and GSM shields

*   xbee = radio, 

        *   device to device or device to computer

what do i need to know about sending/receiving / data / protocols ?

range / power consumption / protocol / network communication

core technologies: 

*   radio

        *   RFID
    *   NFC
    *   zigbee
    *   bluetooth

*   microwave
*   IR

        *   remote control
    *   audio / translation units

*   sonic (ultrasonic)

SPECTRUM, who controls it, who has it, how does it vary, etc.   what sort of laws around spectrum exists.

*

[](http://www.flickr.com/photos/fast-company/3683064554/sizes/o/)http://www.flickr.com/photos/fast-company/3683064554/sizes/o/

![](http://media.treehugger.com/assets/images/2011/10/em-spectrum-chart-080804.jpg)

[](http://media.treehugger.com/assets/images/2011/10/em-spectrum-chart-080804.jpg)http://media.treehugger.com/assets/images/2011/10/em-spectrum-chart-080804.jpg

![](http://www.lbl.gov/images/MicroWorlds/EMSpec.gif)

[](http://www.lbl.gov/images/MicroWorlds/EMSpec.gif)http://www.lbl.gov/images/MicroWorlds/EMSpec.gif