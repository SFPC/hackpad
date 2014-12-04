# Mesh Networks

Happy Hour Mesh Networking with [Sean McIntyre](http://www.boxysean.com/)

![](http://0adb8101b7ae4114a392-dfaacb9b5d3eae26a1de1132d02b2b65.r33.cf3.rackcdn.com/hand-catching-faq-10079690.jpg)

Evernote sucks, Notational Velocity is rad. 

The router is awesome. We have lots of Rasbberry Pis and Arduinos. What about the router!?!

-----

Side quiz:

What is Gentoo? Flavor of Linux - [](https://en.wikipedia.org/wiki/Gentoo_Linux)https://en.wikipedia.org/wiki/Gentoo_Linux

What flavor of Linux is OSX built on? FreeBSD

---

What does flavor of linux mean?

**THE INTERNET**

Flavors of linux:

OSX -> FreeBSD (osx is based on freebsd)

Debian - lots of people develop this, most bad ass of the linux 

Ubuntu -> Debian, made by canonical, trying to make it more user friendly

Raspian

Hardware:

D-Link

Buffalo

Netgear

Cisco -> LinkSys

60 - 100 mhz (level of fast arduinos!)

Is it weird to put Arduino and Raspberry here (under hardware) on the list? Why? No multithreading. That's why it feels different. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_CDSeOdRNfo8_p.150416_1398822958607_20140429_212830.jpg)

Are routers computers? (@lee thinks they are micro- controllers, not computers) [lee t](/ep/profile/m8dzCUlHBtY) is correct!

How fast is your processor on your computer? 2.4 ghz

Arduino? 16 mhz

RaspPi - 500 mhz

Phone - 700 mhz

Which is bigger? Mac! 2.4 billion cycles a second.

hz = 1 cycle per second

60 hz = 60 cycles per second

*   (drunk math... plz help!)

Routers are somewhere between an arduino and a raspberry pi with a radio.

([hackaday.com](https://hackaday.com) plug - who's going to [space](https://hackaday.io/page/276)?)

If you read hack a day for a year, you'll come up with 10 router hacks. they are undocumented arduinos. They are all running propriety ar operating systems. Name another proprietary operating system: windows! when was windows made? early 80s. when were routers made? early 2000s. They have linux on them! all of them!

![](http://i1-news.softpedia-static.com/images/news2/Linux-Outdoor-WiFi-Router-2.png?1341580794)

What can you do on a router? run Python, run C. There's just not a lot of memory (more than an arduino, less than a raspberry pi)

POINT BEING: Routers are a completely hackable platform, and people are hacking them all the time.

![](http://koti.mbnet.fi/~keiky/misc/linux/router/imgs/ethernet_lan.png)

Sean's favorite OS: [OpenWRT](https://openwrt.org/) - OpenWrt is an operating system / embedded operating system based on the Linux kernel, made to work with radio, and primarily used on embedded devices to route network traffic.

VisiBox - 

[Embedded Device](https://en.wikipedia.org/wiki/Embedded_system): An **embedded system** is a [computer](https://en.wikipedia.org/wiki/Computer) [system](https://en.wikipedia.org/wiki/System) with a dedicated function within a larger mechanical or electrical system, often with [real-time computing](https://en.wikipedia.org/wiki/Real-time_computing) constraints.<sup>[[1]](https://en.wikipedia.org/wiki/Embedded_system#cite_note-Barr-glossary-1)[[2]](https://en.wikipedia.org/wiki/Embedded_system#cite_note-2)</sup> It is _embedded_ as part of a complete device often including hardware and mechanical parts. By contrast, a general-purpose computer, such as a [personal computer](https://en.wikipedia.org/wiki/Personal_computer) (PC), is designed to be flexible and to meet a wide range of end-user needs. Embedded systems control many devices in common use today. (microcontrollers)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_CDSeOdRNfo8_p.150416_1398822863416_20140429_214933.jpg)

[7 layers of the network](http://www.freesoft.org/CIE/Topics/15.htm):

*   Physical Layer (wire, fiber-optics, air)
*   Data Link Layer (moving electrons!)
*   Network Link Layer
*   Transport Layer
*   Session Layer
*   Presentation Layer
*   Application Layer

![](http://www.freesoft.org/CIE/Topics/model.gif)

Protocols! - agreed-upon interfaces to connect between different nodes

*   TCPIP
*   Websockets
*   DNS (Domain Name System, aka phone book)

Topologies (very physical concept -> where the internet comes from):

*   wifi router
*   somewhere else in the room
*   60 Hudson st (tribeca)
*   ![](http://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/60_Hudson_Street.jpg/450px-60_Hudson_Street.jpg)

*   California
*   Excellent documentary on where is the physical internet in NYC. By Ben Mendelsohn and Alex Chohlas-Wood - [](https://vimeo.com/30642376#at=0)https://vimeo.com/30642376#at=0
*   (I've head this is good: [](http://www.amazon.com/Tubes-A-Journey-Center-Internet/dp/0061994952))http://www.amazon.com/Tubes-A-Journey-Center-Internet/dp/0061994952)

Regular internet looks like:

![](http://www.boxysean.com/media/images/clocktower-lan/web/current_internet.gif)

**MESH NETWORKS**

![](http://0.tqn.com/d/compnetworking/1/0/-/a/topology_mesh.gif)

A mesh network is a network topology in which each node (called a mesh node) relays data for the network. All nodes cooperate in the distribution of data in the network. It is an agreed-upon protocol for computers to talk to each other in a self healing way, without a centralized structure or authority to manage connections. (I.e. no 60 Hudson st)

Meshes are self assembling networks, or **self healing** networks.  If a node goes down, the network will find a new path to connect nodes. 

![](http://www.johnhenryshammer.com/WOW2/willWebPics/network/selfHealingMesh.jpg)

Centralized (star topology) - DNS (can also run on a decentralized network), HTTP, broadcast radio, twitter (through a single server), roads

De-centralized - runs peer-to-peer on each person's computer - Bit Torrent

Metaphor: the ring road might be faster even if it's not as direct.

There are a number of very large mesh networking the world, not very well publicized. All in Europe - example:

![](http://img.xatakaon.com/2010/11/guifi.jpg)

[Guifi](https://guifi.net/) - this network in barcelona is made possible by rooftop broadcasting antenas.

see how star based it still is? sorta centralized.

Mesh is such a sexy topic. It just sounds etherial and like something you want to do, right? But the biggest mesh networks are politically motivated (less sexy?). Folks in teh Catalan only had dialup, they wanted broadband. So they did mesh to spread teh broadband. Germany had lots of infrastructure mismanaged during iron curtain. Tech savvy folks leapfrogged this by connecting by mesh. 

[Ushahidi BRCK](https://www.kickstarter.com/projects/1776324009/brck-your-backup-generator-for-the-internet) - backup generator for the internet

![](http://ushahidi.com/wp-content/uploads/2014/03/promo-brck.jpg)

Ubiqiti router - you can upload an operating system based around mesh networking on it.

(yes, he's doing this all off the cuff)

[airMaX Ubiquiti](http://www.ubnt.com/airmax)

bidirectional link needs strong signal in both directions. 

Let's talk about Occupy.

This is Isaac:

*   :) [lee t](/ep/profile/m8dzCUlHBtY) link to the documentary!

![](http://assets.vice.com/content-images/contentimage/142369/occupy.jpg)

He made a mesh network for Occupy.

Clear routers - 3g routers for cell network, makes hotspot, 

[Free The Network](http://betabeat.com/2012/03/36466/)

![](http://nyobetabeat.files.wordpress.com/2012/03/freedom-tower.jpg?w=300&h=225)

**MAKING A MESH**

1.  Check what you have on the router already. written on underside. - in our case TP-Link TL-MR3020
2.  look for this name on [openWRT](http://wiki.openwrt.org/toh/tp-link/tl-mr3020)
3.  Go into System Preferences and then open Network. Check your IP address
4.  Open your Network Utility app (find in the search) and click Netstat and run.
5.  Open terminal and enter nmap -sP 192.168.1.0/24 (brew install nmap, if you get a command error)
6.  call [Dan](http://motherboard.vice.com/read/two-years-later-where-is-occupys-internet) on the phone to ask him for passwords/how to reset
7.  In this photo, Dan is on speaker phone. (oh hai —Dan)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_CDSeOdRNfo8_p.150416_1398825010430_20140429_223215.jpg)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_CDSeOdRNfo8_p.150416_1398952586974_20140430_150716.jpg)

Just poke the recessed reset button 10 seconds *after* you first apply  power and hold it down for a couple seconds. The light should start  flashing super fast. Then you should be able to telnet in to 192.168.1.1  using Ethernet.

More on failsafe mode here:

[](http://wiki.openwrt.org/toh/tp-link/tl-wr703n#failsafe.mode)[http://wiki.openwrt.org/toh/tp-link/tl-wr703n#failsafe.mode](http://wiki.openwrt.org/toh/tp-link/tl-wr703n#failsafe.mode)

Now you need to get that file onto the router. The easiest way is just to put it on a usb drive, and then plug it in.

`mtd write -r /usb/openwrt-ar71xx-generic-tl-mr3020-v1-squashfs-factory.bin firmware`

telnet lets you connect to anything that has a tcp/ip access

[mtd](http://www.stlinux.com/howto/Flash/MTD) - [Memory Technology Device](https://en.wikipedia.org/wiki/Memory_Technology_Device)

A **Memory Technology Device** (MTD) is a type of [device file](https://en.wikipedia.org/wiki/Device_file_system#Devices) in [Linux](https://en.wikipedia.org/wiki/Linux) for interacting with [flash memory](https://en.wikipedia.org/wiki/Flash_memory). The MTD subsystem was created to provide an [abstraction layer](https://en.wikipedia.org/wiki/Abstraction_layer) between the hardware-specific device drivers and higher-level applications. Although character and block device files already existed, their semantics don't map well to the way that flash memory devices operate.

really? the os is called Attitude Adjustment?

*    the old version was called white russian...

download squash-factory version of openwrt for your router

scp = copy over ssh,,,

mtd = instead of accessing harddrive > ram instead

have to use so you can flash into firmware

If telnet doesn't work, go into failsafe mode. 

way we pass file to router

*   npm install -g serve (on laptop)
*   run serve at the folder with file (on laptop)
*   (on router) wget [](http://192.168.1.2:3000/filename)http://192.168.1.2:3000/filename
*   cd tmp (to see file there)

ida's password: willcodeforgin

success:

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_CDSeOdRNfo8_p.150416_1398829267739_Screen Shot 2014-04-29 at 11.35.19 PM.png)

BATMAN

COMMOTION [](http://commotionwireless.net/)http://commotionwireless.net/

olsr

Address Space Collision!

Other resources (via Sean):

Slovenia mesh has a great setup page: <[](https://grow.wlan-si.net/wiki/Navodila/Kratka/English)[https://grow.wlan-si.net/wiki/Navodila/Kratka/English](https://grow.wlan-si.net/wiki/Navodila/Kratka/English)>

Biggest mesh in the world map: <[](http://guifi.net/en/node/2413/view/map)[http://guifi.net/en/node/2413/view/map](http://guifi.net/en/node/2413/view/map)>  They actually have started installing fiber onto their network to get  super fast broadband.  AND actually their network is no longer a "mesh",  it was originally using mesh protocols so that they could quickly grow  their network. Now it's top-down managed, i.e., there's a central  authority that manages the links. Mesh becomes unmanagable and does not  scale well when it gets past a few hundred nodes.

Not necessarily a mesh network, but I am really fascinated with packet radio -- it's a kind of low tech mesh system through radio: [](http://en.wikipedia.org/wiki/Automatic_Packet_Reporting_System)http://en.wikipedia.org/wiki/Automatic_Packet_Reporting_System

[](http://www.aprs.org/)http://www.aprs.org/

here you can see objects sending message mapped to google maps: 

[](http://aprs.fi/#)http://aprs.fi/#!lat=38.00000&lng=-97.00000