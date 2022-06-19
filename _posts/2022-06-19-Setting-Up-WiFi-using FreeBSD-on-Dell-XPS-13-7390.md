---
layout: post
title:  "Setting up Wi-FI using FreeBSD on Dell XPS 13 7390"
date:   2022-06-19 06:48:44 -0800
categories: FreeBSD
---

So I recently install GhostBSD on my Dell XPS 13 7390 and had quite an ordeal setting up wifi. 
 
The system was at first unable to load the intel driver, and then loaded the "Killer" driver which is
what was required but for some reason the wifi was still not being recognized. I found with some research that
a little adjustment was required. The default device was "iwlwifi0". 
As usual, you need to know your wifi network name and password and add that info to /etc/wpa_supplicant.conf
<code>
network={
         ssid="myssid"
         psk="mypsk"
}
</code>

then, to get wifi up and running, you need to add two lines to /etc/rc.conf
<code>
wlans_iwlwifi0="wlan0"
ifconfig_wlan0="WPA DHCP"
</code>
<br clear="all">
then reboot or restart server with:
<code>
service netif restart
</code>
and you should be up and running. 
