# Raspberry Pi + OpenFrameworks

**Fairly Detailed Setup Instructions:**

[OF RPi Setup Manual](/D9EgUtoGFWQ)

**Workshop Resources**

[Example Code](https://github.com/jmwohl/OFPiWorkshop)

**OF + Pi SD Card Image:**

[](http://ofpi.jonwohl.com/ofpi_workshop_20140510.img)[http://ofpi.jonwohl.com/ofpi_workshop_20140510.img](http://ofpi.jonwohl.com/ofpi_workshop_20140510.img)

// Note: I'll work on a non-expanded (i.e. not 8GB) image and repost that with instructions when I can.

*   awesome thanks! downloading it now,,, I strumbled upon this link, guess it might be helpful [](http://raspberrypi.stackexchange.com/questions/8305/how-to-make-an-image-img-from-whats-in-the-sdcard-but-as-compact-as-the-ori)http://raspberrypi.stackexchange.com/questions/8305/how-to-make-an-image-img-from-whats-in-the-sdcard-but-as-compact-as-the-ori
*    Nice, this looks promising... I had come across some documentation using parted, but this looks simpler. I'll give it a go.

## Installation

**Transfer image to the SD card**

in terminal, use the application `dd` (if = input file, of = output file)

*   $ sudo dd bs=1m if=/dev/rdisk2 of-backup-image.dmg

These can be any file or memory on your computer, be very careful as ******wrong drive names can damage your files******

**Terminal & how to find the right disk names**

in terminal, _everything_ is a file

*   $ ls

list file in directory

Capital names usually refer to user files

small caps are file that computer use,,, linux stuffs

*   $ /dev 

to access folder with all the drivers

*   ls -al *disk*

(list all the disk)

You'll see a list of disk in your computer

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_HGi1I8lv4s9_p.78223_1399747027328_Screen Shot 2014-05-10 at 2.36.34 PM.png)

different colors represent different permission to each drive

Recommended SD CARD: Lexar 400x Professional: [](http://www.amazon.com/Lexar-Professional-UHS-I-Memory-LSD32GCTBNA400/dp/B007ADFV2M)http://www.amazon.com/Lexar-Professional-UHS-I-Memory-LSD32GCTBNA400/dp/B007ADFV2M

Terminal Software:  iTerm [](http://www.iterm2.com/)http://www.iterm2.com/

Yorgo Alexopoulos has [yorgo.org](https://yorgo.org)

after copy image file you might have to manually expand the partition of the disk,, depends on original SD card size vs your SD card size

**OSC**

kinda of protocol (actually sit on top of another protocol (UDP-based))

a way to send message over the network

**LINK TO SD CARD SETUP MANUAL**

[OF RPi Setup Manual](/D9EgUtoGFWQ)

## Breakdown

*   image was expanded to 8gb, you might need to expand again if you have bigger card
*   wifi dongle >> easily setup go to Raspbian's GUI
*   use package manager to update/upgrade software (Update linux packages section)
*   (add samba support section)

**_tips_**

*   Desolder the LAN port out of the model B to make it draw much less power!
*   long wire soldered to GPIO can make it AM antenna! it's fast enough!

**Pi story**

*   70s everything was exposed // study computer had no barrier

        *   [](http://en.wikipedia.org/wiki/Commodore_64)http://en.wikipedia.org/wiki/Commodore_64

*   it take a lot of work just to get to the same level of exposure on the modern computer

*   sudo arp-scan --interface=bridge100 --localnet

list computer on this networks

*   ssh pi@192.168.2.4

to gain control remotely through SSH

*   cat /dev/urandom > /dev/fb0

write random number to the screen noiseeeeee!

*   cat /dev/zero > /dev/fb0

clear the screen with zero

*   cat /dev/input/mice > /dev/fb0

drag mouse and it draws into the screen by pixels

other interesting folders you want to access

*   /proc
*   /sys

if you want to access gpio1

*   /sys/class/gpio/gpio1

**Samba server**

Finder > Go > connect to server

*   [](smb://192.168.2.2/OF)smb://192.168.2.2/OF

connecting through Samba protocol

this will mount the drive to your computer...

*   what is user/pass
*   config to where to open up to 
*   more about how to put Samba on the pi  [](http://www.openframeworks.cc/setup/raspberrypi/Raspberry-Pi-SMB.html)http://www.openframeworks.cc/setup/raspberrypi/Raspberry-Pi-SMB.html

<undefined><li>GDB another solution for debugging</li></undefined>

[](http://en.wikipedia.org/wiki/Gdbserver)http://en.wikipedia.org/wiki/Gdbserver

## Remote Access

If you are using internet connection sharing, ssh is the way to go

And if you want X, then you can use tightvncserver

But if you want framebuffer, there is only [dispmanx_vnc](https://github.com/hanzelpeter/dispmanx_vnc/), which has a bug where you can't use the mouse :(

I am looking at modifying the source to make sure uinput is being set correctly

But maybe it should be evdev and not uinput? I don't know