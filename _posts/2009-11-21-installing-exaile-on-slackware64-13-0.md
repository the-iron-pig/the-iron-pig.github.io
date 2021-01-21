---
layout: post
title: Installing Exaile on Slackware64 13.0
date: 2009-11-21 23:52
author: woh3
comments: true
categories: [Life]
---
Well, as many of you know, <a href="http://www.slackware.com/">Slackware 13.0</a> is out, and is awesome, and comes with an entirely 64 bit version. Many people use slackbuilds from <a href="http://www.slackbuilds.org/">slackbuilds.org</a> to build packages and when porting over to the 64 bit version there have been a few minor problems in a few packages, usually complaining that it couldn't find some important thing in <strong>/usr/lib</strong>, when we know it should be looking in <strong>/usr/lib64</strong>, this error is because some of the older script functionality passes information incorrectly to the new script options, and hence to get many of these things to compile correctly you need to set the LDFLAGS manually and pass it to the slackbuild script, so I will use an example of compiling the music player <strong><a href="http://www.exaile.org/">exaile</a> </strong>for slackware64 13.0

the command I typed to get it to compile was this:

LDFLAGS="-L/usr/lib64" ARCH=x86_64 ./gst-python.SlackBuild

and it compiled perfectly.

[caption id="attachment_297" align="aligncenter" width="614" caption="exaile on slackware64 13.0"]<img class="size-large wp-image-297 " title="exaile" src="http://www.woh3.com/wp-content/uploads/2009/11/exaile-1024x819.png" alt="exaile on slackware64 13.0" width="614" height="491" />[/caption]
