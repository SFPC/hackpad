# Spacebrew Workshop

[](http://docs.spacebrew.cc/)http://docs.spacebrew.cc/

Our host: Brett Renfer!!!

[](http://www.robotconscience.com/v5/)http://www.robotconscience.com/v5/

 Collins and before that, Rockwell Group 

 What is it?

*    Service and toolkit for interactive spaces.
*    makes it easy to connect things to other things over networks
*   was developed to support prototyping driven design efforts

 Why is it useful?

*   Becomes the glue
*   Enables real time communication
*   A toolkit  with a low floor, high ceiling workflow

 Examples:

*    visualizing human or tech behavior
*   play and interact with living objects (animals, plants)
*   [T](http://www.google.com/aclk?sa=l&ai=CtSUXOdtPVJ_2CqiAsAeO-oCoC-7k3aoGzvOn2M8BqaCQCggAEAEgtlRQvZvXyvz_____AWDJxqmLwKTYD6AB3-nu6gPIAQGqBCBP0LVPF8iKZziuj-3o3uoBjcq_B8G3xkE4ndGO3Y_nzIAFkE6AB_b52SiIBwGQBwKoB6a-Gw&sig=AOD64_0WzMrFk0yr6jeymL74KXRh_5qrXg&adurl=http://www.converged.ciscosolution.net%3FSWAPPID%3D91%26RegPageManagedID%3D787033%26ManagedSWTHEMEID%3D13372%26swcampaignid%3D811848%26utm_campaign%3DCampaign%2520Syndication:%2520Conferencing%2520%2520Video%26utm_source%3DGoogle%2520-%2520Search%26utm_medium%3DPay%2520Per%2520Click&rct=j&q=)elepresence

 Client-Server Model:

*    Server can be your computer or other server (even a small microprocessor Arduino/Pi).
*    Can have one or more "publishers" and "subscriber"
*    Local Network or Online
*   Uses websockets
*   Data formatted at JSON
*   Connected via switchboard - connections can be live/real time swapped

Libraries Available:

*   Processing
*   Arduino
*   OF
*   Python
*   Cinder
*   Unity
*   JS
*   More in the future!

Low Floor and High Ceiling!!! = easy to get started with tremendous growth potential

[](http://docs.spacebrew.cc/examples)**http://docs.spacebrew.cc/examples**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_KlnSWNLoEVO_p.251586_1414520800037_IMG_2708.JPG)

 image: blinking with OF face tracking to turn lamp on/off

 Possibilities

*    spacebrew can get many if not all data types connected to your phone (accelerometer, wifi, range, distance etc) to interact with other items
*   facetracking (winking) to use switches / booleans 

**Using Spacebrew:**

*   the idea is to Silo apps wherever possible.  
*   Make one simple app that can be used with many other simple apps 
*   this simplicity helps *you* when you are working with different programming language

**Prototyping**

*   What's the quickest path to a prototype?
*   Can you use one of existing examples?
*   Or multiple examples?

        *   ex: phone can become a jump sensor, string example can stand in for twitter or text messaging

*   Libraries

        *   Connect to object

*   Publisher: 

        *   //3 arguments (name, type, default value)
    *   type: is boolean, string, range

*   Subscriber: 

        *   //2 arguments (name, type)

**JSON Objects:**

Notes needed here

**Set up your own server:**

*   **From terminal:**

*   install node.js and node dependencies
*   enter:npm install ws
*   enter: cd/Users/akleindolph/Desktop/sfpc/Spacebrew/spacebrew_server  (this should be the route to your spacebrew server folder)
*   enter:npm install forever-monitor
*   enter: node node_server_forever.js
*   change processing sketch (or whatever sketch) to have your IP address or "Localhost"

*   If you want to control things out in the world you'll have to have server space somewhere else: Amazon, google, etc.

*   Amazon web server is free for one year.

*