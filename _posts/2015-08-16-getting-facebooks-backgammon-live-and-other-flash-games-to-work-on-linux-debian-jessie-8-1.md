---
layout: post
title: Getting Facebook's Backgammon Live and other flash games to work on Linux (Debian Jessie 8.1)
date: 2015-08-16 12:47
author: woh3
comments: true
categories: [Debian, FreeBSD, Fun, Life, Software Review]
---
For the past year or so, I have been addicted to the online game <a href="https://apps.facebook.com/cp_backgammon_new/?fb_source=bookmark&amp;ref=bookmarks&amp;count=0&amp;fb_bmpos=_0" target="_blank">Backgammon Live</a> on Facebook, it's fun, the boards are beautiful, and play and features are exciting. Then the people who run the game upgraded the flash requirement to play, and being a Linux user, I was exiled. I tried installing and configuring various other Linux distros like openSUSE (I even tried the official pay version SUSE), Ubuntu, and FreeBSD and PCBSD, but no luck, I could not get flash to work and always ran into this screen on both Firefox and Google Chrome (aka Chromium for Linux)
<a href="http://woh3.motd.org/wp-content/uploads/2015/08/backgammon-live-on-facebook-iceweasel_002.png"><img src="http://woh3.motd.org/wp-content/uploads/2015/08/backgammon-live-on-facebook-iceweasel_002.png" alt="Backgammon Live on Facebook - Iceweasel_002" width="640" height="499" class="alignnone size-full wp-image-1086" /></a>
But after many months, I am back to it, and this is how...
One of my major problems was a software war. Adobe has dropped support for the main open source web browser Firefox, which caused Firefox to declare war on Adobe Flash, and some people think that all this started with an alliance between Adobe and Google, since Google's browser still seems to maintain support. 
So, for the time being, if you are a Linux user, and you want to play Backgammon Live (and other intense flash games) you can only do it through the Chromium browser.
As I said before, I tried Suse, OpenSUSE, UBUNTU versions of Chrome, and nothing worked, but finally under Debian 8.1 (Jessie) I finally got this screen...
<a href="http://woh3.motd.org/wp-content/uploads/2015/08/backgammon-live-on-facebook-chromium_001.png"><img src="http://woh3.motd.org/wp-content/uploads/2015/08/backgammon-live-on-facebook-chromium_001.png" alt="Backgammon Live on Facebook - Chromium_001" width="640" height="499" class="alignnone size-full wp-image-1087" /></a>
The main thing I had to do to get it to work was that I needed Chrome doesn't use the ordinary flash player plugin you get from Adobe, but instead uses "pepperflashplugin-nonfree", so issueing the command in a terminal as root:
<pre><code>apt-get install pepperflashplugin-nonfree
</code></pre>
will install what you need to get back on track. 
