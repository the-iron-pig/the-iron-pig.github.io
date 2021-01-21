---
layout: post
title: Running Minecraft on Opensuse 12.2 64-bit
date: 2012-09-09 14:46
author: woh3
comments: true
categories: [Life]
---
<a href="http://woh3blog.files.wordpress.com/2012/09/anm_minecraft_header.png"><img class="alignnone size-medium wp-image-773" title="anm_minecraft_header" src="http://woh3blog.files.wordpress.com/2012/09/anm_minecraft_header.png?w=300" alt="" width="300" height="108" /></a> with

<a href="http://woh3blog.files.wordpress.com/2012/09/169958-opensuse_chameleon_7_original.jpg"><img class="alignnone size-medium wp-image-774" title="169958-opensuse_chameleon_7_original" src="http://woh3blog.files.wordpress.com/2012/09/169958-opensuse_chameleon_7_original.jpg?w=300" alt="" width="300" height="217" /></a>12.2

Well, all you Opensuse users, who like me, jumped on the upgrade wagon the day 12.2 hit the net soon realized that there is a slight problem with it running Minecraft, namely you login and it just hangs on a black screen. Never fear!

just add the line of code to your .bashrc file
<pre><code>export LD_LIBRARY_PATH="/usr/lib64/jvm/java-1.7.0-openjdk-1.7.0/jre/lib/amd64/"</code></pre>
then reopen bash or just type "source ~/.bashrc" to update the variable and Minecraft should start working fine again. Voila!

<a href="http://woh3blog.files.wordpress.com/2012/09/minecraft-screen.png"><img class="alignnone size-medium wp-image-775" title="minecraft-screen" src="http://woh3blog.files.wordpress.com/2012/09/minecraft-screen.png?w=300" alt="" width="300" height="225" /></a>
