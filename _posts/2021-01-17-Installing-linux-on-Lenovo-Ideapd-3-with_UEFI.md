---
layout: post
title:  "Installing Linux on Lenovo Ideapd 3 UEFI"
date:   2021-01-17 16:48:44 -0800
categories: Linux
---
I have seen thousands of posts with people having problems installing or dual-booting linux and windows on Lenovo machines. Lenovo actually offers linux as one of their shipping options. The main problem is UEFI which <b>HATES</b> Linux. Every-time I leave my system in EUFI mode I have a ton of problems with drivers not working correctly. I have seen quite a few workarounds but for me the simplest and most direct method is to go into the BIOS with holding F2 while rebooting and go to the boot options menu and there are two entries, one allows you to choose UEFI or Legacy, <b>choose Legacy</b>, then under boot priority also switch that one to <b>Legacy</b> and save and reboot with F10. Most of your Linux problems should disappear. 

 
