---
layout: post
title: Slackware 13.37 (ARM) on the Raspberry Pi (B)
date: 2012-06-28 07:22
author: woh3
comments: true
categories: [Fun, Life, Linux, Slackware]
---
Well, I got my <a href="http://www.raspberrypi.org/">Raspberry Pi</a> in the mail today (after ordering it nearly six months ago from Element14), and immediately had to buy and SDCard and a power supply for it.

<a href="http://woh3blog.files.wordpress.com/2012/06/dscn1150.jpg"><img class="alignleft size-medium wp-image-710" title="DSCN1150" src="http://woh3blog.files.wordpress.com/2012/06/dscn1150.jpg?w=300" alt="" width="300" height="224" /></a>

<a href="http://woh3blog.files.wordpress.com/2012/06/dscn1152.jpg"><img class="alignleft size-medium wp-image-711" title="DSCN1152" src="http://woh3blog.files.wordpress.com/2012/06/dscn1152.jpg?w=300" alt="" width="300" height="224" /></a> I got a standard 8gig SD Card, and the power supply had to be a "Micro USB B 5V 750+mA" power supply, I went to Radio Shack in Waikele and got both of them, together they cost me more than the Pi did. The power supply was actually a power supply usually used for cell phones, but works GREAT.

I then used the ArmedSlack-13.37-18.05.2012.zip file, unzipped it, and then with my SDcard loaded as /dev/sdd1 ,I used the command (as root) <pre>dd bs=1M if=/home/will/Downloads/ArmedSlack-13.37-18.05.2012/ArmedSlack-13.37-18-05-2012.img of=/dev/sdd</pre>

to write the image file, after a few minutes the job was done, and I hooked everything up. I connected my lasermouse and my <a href="http://en.wikipedia.org/wiki/Happy_Hacking_Keyboard">Happy Hacker Keyboard</a>, connected the ethernet cable, and powered it on.

<a href="http://woh3blog.files.wordpress.com/2012/06/dscn1166.jpg"><img class="alignleft size-medium wp-image-712" title="DSCN1166" src="http://woh3blog.files.wordpress.com/2012/06/dscn1166.jpg?w=300" alt="" width="300" height="224" /></a>

I got a login shell, and logged in as "root", with password "raspberry" and I was logged in!! Many of you might be surprised that you only get a command line once you log in, and to start the desktop environment (Xserver) you have to type the command :

<pre>startx</pre>

which will load up the default desktop environment XFCE.

<a href="http://woh3blog.files.wordpress.com/2012/06/dscn1157.jpg"><img class="alignleft  wp-image-713" title="DSCN1157" src="http://woh3blog.files.wordpress.com/2012/06/dscn1157.jpg?w=300" alt="" width="300" height="224" /></a>

<a href="http://woh3blog.files.wordpress.com/2012/06/dscn11581.jpg"><img class="alignleft size-medium wp-image-715" title="DSCN1158" src="http://woh3blog.files.wordpress.com/2012/06/dscn11581.jpg?w=300" alt="" width="300" height="224" /></a>

It turns out there was a mistake in the ArmedSlack-13.37-18-05-2012.img IMG file, the guy who put it together left his MAC address in it (I'm sure this mistake will be fixed in future releases), and you wont be able to get ETH0 to come online, even if you run netconfig and ifconfig eth0 will not work, what you have to do before is delete all the contents of the file:

<pre>/etc/udev/rules.d/70-persistent-net.rules</pre>

and then reboot your pi, and eth0 will come online, (assuming you ran ifconfig setting up DHCP etc), once I fixed all that, I was ONLINE!!

<a href="http://woh3blog.files.wordpress.com/2012/06/dscn1159.jpg"><img class="alignleft size-medium wp-image-716" title="DSCN1159" src="http://woh3blog.files.wordpress.com/2012/06/dscn1159.jpg?w=300" alt="" width="300" height="224" /></a>I have seen many you-tube videos of other Operating Systems running slow on the Pi, and Slackware seems faster than all of them, however, the Pi in general is kinda slow, and only serves as an interesting novelty computer. You will not be able to do memory intensive internet activities. It is very cool, and I imagine it can become much more impressive in the future. I found it very useful to login into my shell provider <a href="http://sdf.org/">SDF</a>, via ssh, and that seemed the ideal operating level for the Pi.

PLEASE NOTE: most PI operating systems come with a default username and Password, unless you want people to gain access to your Pi, change the password as soon as it comes on, with the linux shell command :

<pre>PASSWD</pre>
