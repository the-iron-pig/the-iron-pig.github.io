---
layout: post
title: Configuring Wireless on Lenovo S10 ideapad with Opensuse 12.1
date: 2012-03-15 05:40
author: woh3
comments: true
categories: [Life, opensuse, opensuse 12.1, suse]
---
<p>Ok, configuring wireless for the Lenovo S10 ideapad under Opensuse 12.1 can be problematic because the chipsets can easily be confused. On my ideapad yast configuration recognized my wireless card as a BCM4313 but the output of DMESG reported it as BCM4312, and there is a HUGE amount of bad information on the net telling you to just install the BCM43XX drivers and you should (Theoretically) be covered, but alas it is not so! I was actually told by people in the #SUSE irc room on freenode to run the script /usr/sbin/<em>install_bcm43xx_firmware</em> and all my problems should be solved, but they do not realized that MANY ideapads actually have the BCM4312  (Broadcom's BCM4311-, BCM4312-, BCM4313-, BCM4321-, BCM4322-, BCM43224-, and BCM43225-, BCM43227- and BCM43228-based hardware.) chipsets which is NOT supported by the b43, what you need to do is use the <strong>broadcom-wl</strong> drivers also availble in the '<a href="http://packman.links2linux.org/package/broadcom-wl">packman</a>' repository or <a href="http://pkgs.org/opensuse-12.1/packman-i586/broadcom-wl-5.100.82.112-9.9.i586.rpm.html">here</a> and most likely your wireless will magically start working again like mine did.</p><p>Be sure to remove the b43 modules with a command like 'rmmod b43' or remove the packages with 'yast2' because the conflict with the broadcom-wl drivers.</p>
