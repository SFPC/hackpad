# What I think about when I think about SFPC

Or Franc's own hackpad

Things to do:

*   Brainstorm interventions in the physical / urban space

*   Write blog post for CTT
*   Twitter bankrupcy / random walk
*   Exercises in particle systems in oF
*   Some ClojureScript practice (left out here: [](http://clojurescriptkoans.com/#sequence-comprehensions/5))http://clojurescriptkoans.com/#sequence-comprehensions/5)
*   Exercises in swarm behavior in oF

*   Craigslist blogging
*   Draw a map about it
*   Put blog into continuous form for franc.ly
*   Colock
*   Explore possibilities for pong experiment online (spacebrew?)

**Fleeting thoughts**

*   Slowness. I am a compulsive person, and I find easy access, availability of information to be reaching levels of speed that are counterproductive to me. It is a lot easier and enjoyable to read a long *.pdf on an iPad or even on my phone than my laptop, for the simple reason that it is actually *harder* to switch windows. My muscle memory and my compulsion go cmd+T very often, or opening Twitter without even waiting for an order of my reason. Could UX trends evolve in a way that make adjusting usage of software and hardware better suited for concentration and engagement? In a way, dominant business models of the tech world prioritize number of interactions over every other sort of method of interacting with content. This is in fact, due to the way the online advertising industry measures its success and the lack of sustainable business models that don't necessarily exploit weaknesses of human cognition. Although this may sound naive, there has been repeated evidence that most online advertising tactics based on impressions are particularly ineffective. Therefore, there may be systems that function more in sync with the human psyche that allow for a more organic interaction with software and content. 
*   Encoding city real time data into a generative Turing complete.
*   Particle systems, swarms, combination of forces. fun.
*   Spread authorship -> blog on random pages on Craigslist, screenshot it, post the screenshot on Twitter, screenshot it, post it on Facebook, screenshot it, post on Github, screenshot it and post the picture on my blog.

**Explorations around collective agency, authorship, action, decision-making and participation, swarm behavior & theory**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_WJ9NJQifQni_p.252083_1413824169515_undefined)

Swarm. 

_noun \ˈswȯrm\_

*   A large number of animate or inanimate things massed together and usually in motion.

Swarm behavior

*   1. Collective behavior exhibited by animals of similar size which aggregate together and are in motion.
*   2. In mathematical modeling, an emergent behavior arising from simple rules that are followed by individuals and does not involve any central coordination.

[](https://en.wikipedia.org/wiki/Swarm_intelligence)https://en.wikipedia.org/wiki/Swarm_intelligence

**Concepts**

Swarm intelligence / Collective intelligence / Collaborative intelligence

Collective decision making

Folksonomy (meh)

**Questions to answer**

*   What are the features that allow agency in collectivity to emerge?
*   How does it happen? What does it require?
*   When does collective agency emerge?
*   Can it be replicated?
*   The prefix "Crowd", crowdstuff: crowdsourcing, crowdfunding, crowd_tax_evasion (aka bitcoin)
*   Open questions about assistive technology

**Hints on where to look for the swarm magic (in humans)**

*   Loren Carpenter Pong experiment
*   Political manifestations and power structures:

        *   15M, Tahrir, Occupy
    *   Political manifestations: decentralization, civic society, protests, riots
    *   Military manifestations?
    *   Tweaks to our concepts of property and interaction change the emerging behaviors of our societies and are at the core of political ideologies. 

*   Rave culture

And emergence

Wikis and open-source everything

Urban environments

**Online communities**

*   Tumblr communities and subcultures
*   Meme culture (9gag, whatever else)
*   Reddit, 4Chan
*   Patterns and swarms on data from Craigslist

**Ideas for projects**

*   Explore swarm behavior algorithms (flocking and others)
*   Generate collective action using an online platform
*   Replicate Loren Carpenter, SIGGRAPH's 91 experiment on web.
*   Generate collective action in the physical space.
*   Model swarm behavior happening in the physical space.
*   When does crowd work better than individuals? When is the sum greater than the parts?

**Algorithms and models for swarm behavior**

In the late 1980s, computer scientist [Craig Reynolds](http://www.red3d.com/cwr/boids/) developed algorithmic steering behaviors for animated characters. These behaviors allowed individual elements to navigate their digital environments in a "lifelike" manner with strategies for fleeing, wandering, arriving, pursuing, evading, etc. Used in the case of a single autonomous agent, these behaviors are fairly simple to understand and implement. In addition, by building a system of multiple characters that steer themselves according to simple, locally based rules, surprising levels of complexity emerge. The most famous example is Reynolds's "boids" model for "flocking/swarming" behavior.

Examples of swarm-like things:

*   [](http://forum.openframeworks.cc/t/boids/1028)http://forum.openframeworks.cc/t/boids/1028
*   [](http://vimeo.com/2131989)http://vimeo.com/2131989 (oF)
*   [](http://vimeo.com/1241853)http://vimeo.com/1241853 (oF)
*   FIELD studio (www.field.io) has a lot of projects like that.

<undefined><li>**Mathematical games**</li></undefined>

Langton's Ant

John conway's Game of life

"When a square is dead and comes to life, that is "movement" from state 0 to state 1.  It takes with the the power of the live cells around it to influence the life of the cells around it.  This is transference of power specifically called for in the basic rules, a transference of identity called "life" as "coming alive".  Movement is clearly contained in that event, as well as reproduction.  The same with the movement from life to death.  But each cell truly lives out its life only in these alterations of 0 and 1.  Sometimes a cell dies, and a new cell is born in its place, perhaps from the same dynamic, but from different cells now enacting it. Sometimes this does not happen, as in the simple four cell square, which is immortal if undisturbed.  The ideas of motion and reproduction which take hold of our perceptions and thinking when we look at larger scale, more complex or perhaps intricate forms, is a projection of those ideas.  The substrates themselves do not "move" or "reproduce" in those ways. The formal structure is all that "moves" and "reproduces". The "content of life" is not present in that alone."

-- some dude, in some blog, commenting 

Concepts:

*   [](https://en.wikipedia.org/wiki/Perlin_noise)https://en.wikipedia.org/wiki/Perlin_noise

Videos, illustrations, diagrams of something that may be tangentially related to something related to this:

*   [Dancing dude](https://www.youtube.com/watch?v=GA8z7f7a2Pk)

OpenFrameworks examples:

*   [](http://forum.openframeworks.cc/t/experimenting-with-boids-flow-fields/811)http://forum.openframeworks.cc/t/experimenting-with-boids-flow-fields/811
*   [](http://forum.openframeworks.cc/t/3d-swarm/966)http://forum.openframeworks.cc/t/3d-swarm/966

Cinder (but easy to use for oF)

[](http://libcinder.org/docs/v0.8.4/flocking_chapter1.html)http://libcinder.org/docs/v0.8.4/flocking_chapter1.html

[](http://libcinder.org/docs/v0.8.4/hello_cinder.html)http://libcinder.org/docs/v0.8.4/hello_cinder.html

**Intelective intelligence, collective decision making and political process**

[](https://medium.com/matter-archive/is-the-internet-good-or-bad-yes-76d9913c6011)https://medium.com/matter-archive/is-the-internet-good-or-bad-yes-76d9913c6011

**References**

*   [Steven Strogat](https://en.wikipedia.org/wiki/Steven_Strogatz)
*   "The Interventionists: Users' Manual for the Creative Disruption of Everyday Life"
*   [](http://www.theswarmlab.com/)http://www.theswarmlab.com/
*   [Situationsts](https://en.wikipedia.org/wiki/Situationist_International)
*   Wanderlust projects: [](http://wanderlustprojects.com/)http://wanderlustprojects.com/
*   Kevin Kelly, [Out of Control, ch2: The collective intelligence of a mob](http://kk.org/outofcontrol/ch2-b.html)
*   [Nature of code: Autonomous agents](http://natureofcode.com/book/chapter-6-autonomous-agents/)
*   Loren Carpenter Pong experiment
*   [Dancing Plague of 1518](https://en.wikipedia.org/wiki/Dancing_Plague_of_1518)
*   Flocking images: [](https://www.youtube.com/watch?v=XH-groCeKbE)https://www.youtube.com/watch?v=XH-groCeKbE
*   Modeling swarm behavior: [](http://phys.org/news11060.html)http://phys.org/news11060.html
*   [](http://www.theswarmlab.com/emergence-on-radiolab-august-14-2007/)http://www.theswarmlab.com/emergence-on-radiolab-august-14-2007/

**Tools**
<undefined><li>**Languages, services, toolkits**</li></undefined>

Spacebrew

Cinde

openFrameworks

Arduino
<undefined><li>**Editors**</li></undefined>

[](http://markable.in/editor/)[http://markable.in/editor/](http://markable.in/editor/)

iA Writer

Sublime

We
<undefined><li>**Productivity**</li></undefined>

Todoist

OmniFocus