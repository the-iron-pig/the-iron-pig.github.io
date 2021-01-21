---
layout: post
title: Configuring Wireless on Lenovo S10 Ideapad under Opensuse 13.1
date: 2014-01-16 17:55
author: woh3
comments: true
categories: [Life, Linux, Opensuse, Security, Software Review]
---
So, some of you still have Lenovo S10 Ideapads, and with the new release of Opensuse 13.1, some of you found out wireless doesn't work straight out of box, well, never fear, the solution couldn't be simpler. It turns out that Opensuse 13.1 is already preconfigured to work with your wireless, except for the one tiny detail of chipset firmware. The Lenovo S10 Ideapads use the&nbsp;Broadcom Corporation BCM4312 chipset, and all you have to do it download and install the firmware for that chipset, put it in the right folder, and then either restart your computer, or load the modules with modprobe, and your wireless should be working. The wonderful people at Opensuse already created a PRE_INSTALLED script to locate, download and put the firmware in the correct directory for you already, just run the script (command)

<pre><code>install_bcm43xx_firmware</code></pre>

you can just copy and paste the above command if you like, be sure that you are root when you run the command. Once the script is finished you can either restart your computer, or load the module manually with the command:

<pre><code>modprobe b43</code></pre>

and, just as happened to me, your wireless should come to life. If all of that fails, please be sure to check that you do not have the "Airplane Mode" button clicked off (on), it turns off your wireless in hardware, its a little button with a green computer picture on it with radio wave symbols radiating from it.
