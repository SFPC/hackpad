# OF + RPi Setup Manual

References

[](http://www.openframeworks.cc/setup/raspberrypi/Raspberry-Pi-Getting-Started.html)[http://www.openframeworks.cc/setup/raspberrypi/Raspberry-Pi-Getting-Started.html](http://www.openframeworks.cc/setup/raspberrypi/Raspberry-Pi-Getting-Started.html)

## Preparation
<undefined><li>Things you'll need on hand:</li></undefined>

1.  A Raspberry Pi with appropriate usb cable for power.
2.  A blank 8+ GB SD card, the faster the better. I've been using a **Lexar Professional 16GB 10/400x Speed **card with good results, but any fast SD card should be fine.
3.  A USB keyboard for the Pi
4.  A screen for the Pi, either an HDMI monitor or a screen with a composite input.
5.  A WiFi dongle for the Pi

## Installation and Setup

**Install linux on your SD card**

Reference: [](http://elinux.org/RPi_Easy_SD_Card_Setup)[http://elinux.org/RPi_Easy_SD_Card_Setup](http://elinux.org/RPi_Easy_SD_Card_Setup)

First, grab the latest image of Raspbian Debian Wheezy from the RaspberryPi site: [](http://www.raspberrypi.org/downloads/)[http://www.raspberrypi.org/downloads/](http://www.raspberrypi.org/downloads/)

Insert the SD card into the slot on your computer, or use a card reader. On mac, go to the terminal and take a look at the available disks in order to find the SD card:

*   $ diskutil list

This will show a list of all of the disks:![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_lNjZ1a9zgk2_p.89063_1398531907152_Screen%20Shot%202014-04-26%20at%201.04.40%20PM.png)

From this list you should be able to determine which disk is the SD card (look at the name and size). In my case it was **/dev/disk6**, so that's what I'll be using here, but yours will very likely have a different number.
<undefined><li>**<u>It is VERY IMPORTANT that you get the path of the SD card correct! A mistake here could result in the loss of your entire hard disk!</u>**</li></undefined>

Now that we know the path to the disk, lets unmount it so that we can overwrite it:

*   diskutil unmountDisk /dev/disk6

Finally, we'll us dd to overwrite the SD card with the Raspian image:

*   sudo dd bs=1m if=2014-01-07-wheezy-raspbian.img of=/dev/disk6

This will take several minutes (maybe 10? 20?). Be patient. Once it's done, it's ready for your Pi. Eject the SD card (probably now called 'boot') from your computer and stick it in the Pi. Plug in the Pi's power, a keyboard, monitor, and WiFi dongle, and start 'er up!

**Basic Pi Configuration**

Upon initial startup you'll be kicked into the Pi's configuration program. You can get back here anytime from the command line by typing `raspiconfig`. We're going to make some changes in here.
<undefined><li>1 Expand the Filesystem</li></undefined>

First first option is to expand the filesystem, which we want to do. Press enter and wait a couple seconds for it to finish. (This does exactly what it sounds like.)
<undefined><li>2 Change the User Password</li></undefined>

We'll change the default user password to **pi**. Yeah, **user: pi, password: pi**. We're clearly security experts.
<undefined><li>3 Internationalisation Options</li></undefined>

If we're in the US, we do want to change this. By default, Raspian Wheezy is setup for a GB keyboard as opposed to US — this hung me up when I was trying to enter a WiFi password with special characters and couldn't for the life of me find them. I changed my Local to **en_US.UTF-8**, set my timezone to **US - Eastern**, then changed my keyboard to **English (US) - English (Macintosh) **because I'm using an old Mac keyboard.
<undefined><li>4 Force audio output</li></undefined>

You may or may not want to do this. By default the Pi will automatically send audio where it thinks you want it, either to the audio jack or the HDMI output. For my purposes, I wanted to ensure that all audio was sent out of the audio jack, even if I was using the HDMI output for my monitor. This can be set under Advanced Options->Audio.

**WiFi Setup**

1.  Plug in the wifi dongle.
2.  Log into the Raspbian GUI: `$ startx`
3.  Double click the WiFi Config application on the Desktop and go through GUI wifi setup steps.
4.  Log out of the terminal.

**Update Linux Packages**

Now that we're connected to the interweb, let's update the software that's already installed on the Pi.

*   $ sudo apt-get clean
*   $ sudo apt-get update -y
*   $ sudo apt-get upgrade -y

Each of the steps might take a little while to complete.

**Add Samba Support**

Adding a samba server to the Pi will let you mount it on your computer as a remote drive. This is a good way to share files between the Pi and your computer, and can let you edit files directly on the Pi using your preferred editor. Rather than repeat the steps here, just follow this guide:

[](http://www.openframeworks.cc/setup/raspberrypi/Raspberry-Pi-SMB.html)[http://www.openframeworks.cc/setup/raspberrypi/Raspberry-Pi-SMB.html](http://www.openframeworks.cc/setup/raspberrypi/Raspberry-Pi-SMB.html)

**Install and Compile openFrameworks**

Navigate to the user home directory and install the latest release of OF.

*   $ cd
*   $ mkdir openFrameworks
*   $ curl -O [](http://www.openframeworks.cc/versions/v0.8.1/of_v0.8.1_linuxarmv6l_release.tar.gz)[http://www.openframeworks.cc/versions/v0.8.1/of_v0.8.1_linuxarmv6l_release.tar.gz](http://www.openframeworks.cc/versions/v0.8.1/of_v0.8.1_linuxarmv6l_release.tar.gz)
*   $ tar xfz of_v0.8.1_linuxarmv6l_release.tar.gz -C openFrameworks --strip-components 1

Now we'll install the OF dependencies and compile the framework.

*   $ cd ~/openFrameworks/scripts/linux/debian_armv6l
*   $ sudo ./install_dependencies.sh -y

You'll get asked some questions during this install, just blindly answer yes. Once that's done, we're ready to compile. **This next step takes a loooong time, on the order of an hour.** Once you kick it off, go get lunch.

*   $ cd && sudo make Release -C /home/pi/openFrameworks/libs/openFrameworksCompiled/project

**Run your first OF app on the Pi!**

Whew, you made it. Let's try building and running one of the examples.

*   $ cd ~/openFrameworks/examples/graphics/polygonExample
*   $ make
*   $ make run

The `make` step is where the actual application gets compiled. It might take a few minutes. When it's complete it will give you some little instructions, one option of which is `make run` which will run the application. Woo hoo!