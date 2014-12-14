# Poetic Science Fair PDF

**Background on SFPC**

School for poetic computation is an independent school that meets for two terms per year in New York City. We are a 10 week program for artists, designers, writers and engineers to learn programming as a medium for self-expression, on par with the disciplines of Music, Painting and Sculpting. We help practitioners expand their discipline by examining how their respective crafts can both inform and be informed by coding literacy.

**Poetic Science Fair**

The Poetic Science Fair, was one day event designed to share learning about technology, art and poetry with middle and high school students. Participants were invited to design drawing robots, record sound maps of the neighborhood, make light up jewelry, play card games and teach computers to read poetry. This publication documents the five workshops prepared for the event and we hope that this might be a useful guide for educators who want to develop their own poetic computation curriculum.

Poetic Science Fair was open to the public, for anyone interested in open source technology, arts and craft, and music and sound.  This event was hosted at Silent Barn, an independent art and music space in Bushwick, Brooklyn. All workshops were free for youth under 18 years old.

All workshops take from 0.5 - 2 hours and are designed for groups of up to 7 people. 

Younger the kids the more adults needed (kids under 10, 3 to 1 kid to adult ratio). Middle school kids - groups could be bigger with less adults. 

**Workshop Outlines**

**Code Poetry Jam**

Artist: Todd Anderson 

Length:_ _1 hour

Size: 2-6 people

_Description_

Code an audio-visual poetry machine that will continue to live on the internet! Participants will write some javascript and rhymes for the computer to perform. They will match lines to GIFs to create poetry bots that run in a browser. Total beginners can hack on existing templates.

_Materials needed_

*   Several computers
*   Code from this repository: repo and instructions (link here)
*   Folder of GIFs and beats (included in repository)
*   Either a large monitor or projector for performing projects

_Steps_

*   Install code on an http server as described in the repository ( we used a node server, it seems to work a little better than the python http server)
*   Run the http server in the silent barn workshop folder
*   Send the browser to [](http://localhost)http://localhost  (8080 for node and 8000 for python)
*   Run through demo script (you might want to practice with this before hand)
*   Demo the code platform - walk them through the code and show them the parts to be modified. Focus on the key bindings section where the rhymes are input.
*   Breakdown one of the Mousetrap bindings. Specifically looks at functions speakNspell (says the word and shows the word) and the showGif (shows GIF). Can scroll down to briefly look at what is going on withthe functions.
*   Change the speakNspell function to a rhyme relating to a student.
*   More advanced students can modify these functions (end of code). This is the next step to modifying the performance.
*   Can change voice, and speed etc.
*   Outcomes can be geared towards either a performance or publication of each students javascript (you would need to create a directory on a webserver where each project has a javascript and html file to publish.)

_Reflections on this workshop_

*   Deals with a range of skill levels well, scales up.
*   Even those who claim they cant code, this exercise has a low barrier to interacting with the code for an engaging outcome.
*   Editing javascript in sublime text 2 is helpful for iding syntax problems. Then refresh browser to see the outcome.
*   Encourage helping each other.

**Light Jewelry**

Make a wearable circuit.

Artist: [Lauren Gardner](http://poohead.com/), [Yuki Yoshida](http://sfpcyukiy.tumblr.com/), [Rachel Rose Ulgado](http://cargocollective.com/ulgado), [Paige DeRaedt ](http://paigederaedt.weebly.com/)

Size: Up to 8

Length:_ _30-60 minutes 

Description

Make light-up felt wearables with simple circuits. Participants will sew and glue together felt adornments that contain simple LED circuits.  

_Materials needed_

*   LEDS of all colors
*   3V Batteries such as these: [](http://www.amazon.com/Maxell-Lithium-Batteries-Size-CR2025/dp/B002E0DSBW)[http://www.amazon.com/Maxell-Lithium-Batteries-Size-CR2025/dp/B002E0DSBW](http://www.amazon.com/Maxell-Lithium-Batteries-Size-CR2025/dp/B002E0DSBW) 
*   Felt
*   needle & thread (different colors) 
*   Cardboard
*   Safety pins
*   Packing tape
*   Bobbie pins for hair pieces

_Steps_

*   Design and cut felt shapes
*   Construct circuit. These are constructing in a similar way to LED throwies. See these instructions: [](http://www.instructables.com/id/LED-Throwies/)http://www.instructables.com/id/LED-Throwies/.  
*   Attach electronics to felt shapes
*   Sew/glue piece in place
*   Add finishing touches

_Reflections on this workshop_

For very young kids (~6 yo) it was helpful to have parents around, some were shy so this helped break down barriers and get them thinking more creatively. This would probably be difficult for kids under 6. The barrier seemed to be operating scissors and needles. Kids really wanted to use needle and thread rather gluing. 

We needed more batteries. It would be good to figure switches or rechargeable batteries. 

**Binary Card Game**

Artist: [Toru Urakawa](http://sfpctoruurakawa.tumblr.com/) with help from [Franc Camps-Febrer](/ep/profile/qGBM7d6h8Ht) and Nick Barr 

Size: 4 people per session. 

Length:_ _30min

_Description_

Learn to play mysterious card game about binary numbers. This game is played with a custom deck of cards that was created using the webservice ([](http://www.makeplayingcards.com/))http://www.makeplayingcards.com/). The deck contains 54 cards, 27 are white and others are black. Players turn over their hand and calculate scores based on binary numbers, the player with the highest wins the cards played in that hand. The player with all the cards at the end of the game wins. To help the players score their hands, the game is to be accompanied by a binary counter that translates the binary sequence from the cards to base 10 numbers. This counter is published online here: [](http://franc.ly/bica/index.html)http://franc.ly/bica/index.html

This card game is part of a larger project developing card games for learning binary numbers. The project is documented here: [](https://github.com/toruurakawa/Encyclopedia-of-Binary-Card-Games)https://github.com/toruurakawa/Encyclopedia-of-Binary-Card-Games

_Materials needed_

Custom pack of black and white binary cards

_Steps_

*   Players play the top card from their deck at the same time.
*   Black beats White; the player who plays the black card takes both
*   If the players play the same card, they place the next 3 cards faceup; the sum of those cards decides the winner.
*   Players keep playing until their deck is empty; at that point they take all the cards that they won; this becomes their new deck.
*   Gameplay continues until 1 player has all the cards

_Reflections _

Players enjoyed the game more than I expected. It worked to engage people who are not normally interested in media arts. One of the participants were inspired to develop his own card game which is documented in the repository.  

**Listen Up, It’s Bushwick!**

Sound walk and recording workshop to create a sonic map of your neighborhood.  

Length:_ _2 hours

Artists:_ _Zachary Dunham, Ida Benedetto, Taeyoon Choi      

Size: 7 people

_Description_

How do we experience the sounds of our neighborhood? Which are the sounds that define it? By making simple recordings from a walk around your neighborhood, and thinking about the ways in which sounds demarcate and blur geographical boundaries, we can create a unique experience with these sounds. Recorders are placed on an enlarged physical map and are easily played back though pressing the simple recorders mounted to the map.

_Materials needed_

*   Sound recorders ([](http://amzn.to/1zVCi8m))http://amzn.to/1zVCi8m)
*   4X 32"X40" White Mat Board
*   Projector and adaptor if needed for HDMI/Thunderbolt 
*   Box of pencils, colored markers (any) 
*   Tape (Duct and White Masking Tape)
*   8 Pack of AA batteries 
*   Double sided velcro
*   Colored felt

_Steps_

_Note: Step 1 is optional. It's easy to do the workshop without hacking the recorders.  Doing requires additional time, and assumes some basic electronics experience.   _

1.) Recorder Hack  

Remove the speaker top and connect a button to two wires.  Connect one wire to the VC pin and the other wire to C3.

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fp9MHX3ixnM_p.251746_1416610759208_IMG_1036.jpg)

Add a speaker to the red and black wires and replace the top.  

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_fp9MHX3ixnM_p.251746_1416610814247_IMG_1035.jpg)

Remove the speaker top and connect a button to two wires.  Connect one wire to the VC pin and the other wire to C3.

2.) Assemble the Bare Map.

*   Hang the mat board on a wall 
*   Using a projector, project a simple map to help sketch streets, and boundaries for your map.

3.) Discussion and Sound Walk 

*   Brainstorm as a group about the sounds you think define the neighborhood.  
*   Place pins on the map where you think you might find these sounds.  
*   As a group or individually, spend 45 minutes walking, listening and recording these sounds.  
*   Return to the map and decorate it with the recorders using double sided velcro.  

_Reflections on this workshop_

*   Leave enough time to meet, discuss, talk about the neighborhood.  
*   The workshop can be lead in a linear manner as described above or more freeform. This approach would allow participants to visit the map, take a recorder out to the neighborhood on their own, record a sound and return to the map. Over the course of an afternoon or a day the map becomes populated with additional sounds and returning participants can be surprised by each other's recordings  

**Simple Machines**

Make a drawing robot

Artist: Andrew Kleindolph with help from Tega Brain, Taeyoon Choi,  Luke Demarest.

Length: 1-2 hour  

Size: (depends on age) 6 kids

_Description_

(pedagogical aim)

What can you do with a single motor and basic physics that creates a situation where students design and make decisions for a creative result. 

Motors are the core element creating motion in all machines.  This workshop starts by looking at how electricity makes a motor turn and how electricity can be rerouted to change the direction of the motion.  Once we have some DC motors turning, we’ll connect them to various cardboard structures that will make their motion into something “useful”.  In a short time, participants can have working fans, basic robots, kinetic displays or simple drawing machines. At Silent Barn, participants created machines for drawing.

_Materials needed_

Various Small DC motors (Taeyoon) (~6v anything between 3-9 volts) These one's were best - [](http://www.pololu.com/product/188)http://www.pololu.com/product/188 

Motor hubs (we used these: [](http://www.pololu.com/product/1996))[http://www.pololu.com/product/1996](http://www.pololu.com/product/1996))

4.5v and 9v battery packs

Hook up Wire

Balsa Wood

Hot Glue

Basic switches

Sculpture wire

Large/soft markers

Large paper

Duct tape

Balsar wood

_Steps_

*   Review handout instructions
*   Review example robots
*   Talk about vibration and motion is created. How weight can be offset to create rotation. 
*   Solder the wires to the motor, batterie pack and switch
*   Ideally participants would draw their robot
*   Cut, glue and wire robot houseing together. 
*   Test
*   Reconstruct (and repeat)

_Reflections / Notes_

Example bots is really important. 

In general some of our motors were not strong enough, the gear motors (which are more expensive) were better, link above. Motor strength is important. 

Younger kids need assistance and supervision using soldering irons. This workshop needs close supervision because of soldering irons. 

We could have used more paper.

We covered all the battery packs, the switch box (most flat surfaces) with colored felt plates. This makes these components more approachable and tactile, fuzzy, fun?