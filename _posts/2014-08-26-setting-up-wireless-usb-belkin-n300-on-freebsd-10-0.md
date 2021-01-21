---
layout: post
title: Setting up wireless usb Belkin n300 on FreeBSD 10.0
date: 2014-08-26 19:46
author: woh3
comments: true
categories: [FreeBSD]
---
Well, this was an interesting experience, and eventually someone on irc channel #freebsd pointed out to me that the wired connection was taking dominance over my wireless connection, so I commented out the eth0 (fxp0) entry in my /etc/rc.conf, it, when it rebooted, it was using only the wireless. :-)

It was such a pleasure to see the little green flashing light come one. the kernel recognizes the needed software for Belkin n300 F9L1002v1

and uses the rsu module, which designates the wireless usb as <strong>rsu0</strong> (you will need to add the module load statement
<pre><code>
if_rsu_load="YES"
</code></pre>

to your /boot/loader.conf) and you need a wpa_supplicant.conf file in /etc that has
<pre><code>
network={

ssid = "your Network ID"

psk="password"

}
</code></pre>

then enable some changes in your /etc/rc.conf

to include:
<pre><code>
linux_enable="YES"
wlans_rsu0="wlan0"
ifconfig_wlan0="ssid <em>your-ssid-here</em> WPA DHCP mode 11g"
dhcp6c_enable="YES"
</code></pre>
then reboot, and when the system comes up, do
<pre><code>
ifconfig wlan0 up
</code></pre>
and you should be running. I added the dhcp6_enable statement because my Comcast Xfinity wireless modem uses ipv6 addressing, your config may not need that.
