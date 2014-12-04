# the internets

[wtf is] the **internets**?

*   facebook
*   connecting computers +1

*   **networks of networks**
*   tcp/ip
*   **wires** // its physical
*   gifs and cats
*   a communication protocol to send data between computers in disparate locations

what's the **world wide web**?

*   things you put in front of the url (www.) +1

        *   [](http://no-www.org/)http://no-www.org/
    *   [](http://www.yes-www.org/)http://www.yes-www.org/

*   address pointers to where things are stored digitally on disparate computers on the network
*   servers
*   body of knowledge managed by straaaange people
*   protocols
*   **public internet** +1

"Things that are addressable over http"

## wires

There is a physical presence to the internet. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_hqAiuJMmBGV_p.78223_1398361740082_undersea_cable_map.png)

![](http://sleepout.com/nomad/wp-content/uploads/2013/10/roll-out.jpeg)

Created by DARPA 

We tried a few things: 

*   ping yoursite.com
*   curl yoursite.com

**http response codes:**

[](https://developer.mozilla.org/en-US/docs/Web/HTTP/Response_codes)https://developer.mozilla.org/en-US/docs/Web/HTTP/Response_codes

*   For example a "404" error is "Not Found –  Server can not find requested resource. This response code probably is most famous one due to its frequency to occur in web."

Making HTTP requests in the terminal:

[](http://blog.tonycode.com/tech-stuff/http-notes/making-http-requests-via-telnet)http://blog.tonycode.com/tech-stuff/http-notes/making-http-requests-via-telnet

**Vintage Terminal Emulator for Mac and iOS: Cathode**

[](http://www.secretgeometry.com/apps/cathode/)http://www.secretgeometry.com/apps/cathode/

![](http://www.secretgeometry.com/media/iPhone5cCathodeFlatOptimized.png)

"BACK TO THE FUTURE Disregard decades of user interface progress."

*   ifconfig en0 //to look up own ip address

[](http://www.kimonolabs.com/)http://www.kimonolabs.com/

An easy tool for creating APIs for pages where there is none. 

We used the following code to pull a specific image from the Met database using the api from [](http://scrapi.org)http://scrapi.org

*   JSONObject json;
*   PImage img;
*   String image_url="";
**   void setup() {
*     json = loadJSONObject("[](http://scrapi.org/object/81781)http://scrapi.org/object/81781");  
*     img = loadImage(json.getString("image"));
*     size(img.width,img.height);
*   }
**   void draw() {
*     image(img, 0, 0, img.width/4, img.height/4);
*   }

**Assignment:**

Use two different pieces of data that [don't require authentication] and combine them to make a 'data visualization.' 

*   **Potential APIs:**

And here's this: [](http://casperjs.org/)http://casperjs.org/

API Tutorial: [](https://zapier.com/learn/apis/)https://zapier.com/learn/apis/