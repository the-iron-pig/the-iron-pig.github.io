---
layout: post
title: Some pointers for compile problems on Slackware64 13.1
date: 2010-07-11 23:38
author: woh3
comments: true
categories: [Life]
---
As many of you know I run slackware64 13.1 on my computer, I recently converted my system to multi-lib via alienbobs tutorial which I highly recommend <a>here</a>.
Many people have been running into compile problems with some of the build scripts that can be found at <a href="http://slackbuilds.org/">slackbuilds.org</a>, particularly for the 64-bit version of the software, even when people add the switch:
<pre><code>ARCH=x86_64 ./whatever.slackbuild</code></pre>
they still get failed compiles, if you look through the output of the buildscript it is usually because the script, even though it was told to look in 64 bit library path for dependencies, still does not, and is actually looking in /lib instead of /lib64. I ran into this problem building transcode from <a href="http://slackbuilds.org/">slackbuilds.org</a> and as I said above I am running multi-lib, so it failed because it was finding the 32-bit versions instead of the 64-bit version of dependencies it needed and errored out giving "could not read symbols" error. The cure for this problem on 64-bit slackware 13.1 is to add an additional switch called LDFLAGS  to buildscript that points to your 64-bit libs like this:
<pre><code>LDFLAGS=”-L/usr/lib64″ ARCH=x86_64 ./gst-python.SlackBuild</code></pre>
and with that the gst-python and transcode and other slackbuilds started compiling correctly.
