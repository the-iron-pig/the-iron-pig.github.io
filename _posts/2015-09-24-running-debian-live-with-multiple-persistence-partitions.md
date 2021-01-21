---
layout: post
title: Running Debian-Live with Multiple Persistence Partitions
date: 2015-09-24 01:19
author: woh3
comments: true
categories: [Debian, Fun, Life, Linux, Privacy, Security]
---
So I am now running a USB Drive with Debian-Live 8.2.0 on it, and it is pretty darn cool. I am running it with Persistence, which allows me to save files and information between reboots, so my preferences and changes to the system actually Persist over time.

If you have tried running Debian-Live, you probably know that for it to have Persistence, you need to have a persistent partition named live-rw, and that is all well and good and it works fine, but what I have done is set it up so that I actually have a third partition that mounts as /home. during my research, I found this bit of information on <a href="http://live.debian.net/manual/1.x/html/persistence.html" target="_blank">Debian Live wiki</a>...
<div class="section" title="7.5.2. Home automounting">

<em>If during the boot a partition (filesystem) image file or a partition labeled <span class="command"><strong>home-rw</strong></span> is discovered, this filesystem will be directly mounted as <span class="command"><strong>/home</strong></span>, thus permitting persistence of files that belong to e.g. the default user. It can be combined with full persistence.</em>

It turns out that information is NOT CORRECT. Since the writing of that manual there have been changes in how Persistence is implemented, so I am going to tell you how to do it right.

First, follow the instructions for making a Debian Live USB drive found on <a href="http://www.vleeuwen.net/2014/01/create-a-persistent-debian-live-usb-flash-drive" target="_blank">Dirk-Jan's Blog</a> , I tried several different tutorials, and ultimately the steps on his blog are the quickest and easiest, the only difference is that instead of just making the 2 partitions he tells you to make, you are going to make 3 (or more if you wish).

One partition must be FAT-32 to actually hold and run the Debian-Live iso, the live-rw partition can be EXT2 or EXT4 (where persistence files will be kept), and the parition you wish to use as /home can be  EXT2 or EXT4.

I have a 15 GB USB stick, I gave it 3 partitions, sdb1 = FAT 32 (bootable flag = yes) 3GB,  sdb2 = EXT4 Peristence, labeled as 'persistence' 3 GB, and sdb3 = EXT4, labeled also as 'persistence', ~9 GB.

I followed all the steps on Dirk-Jan's blog, and it is fairly straightforward, but the thing you need to remember is that every partition that you want to mount persistently needs to be labeled 'persistence' (you can do this using 'gparted' steps of his blog) and the / of each partition you want mounted needs to have a file called "peristence.conf" that basically contains one string of information, where on the Debian-Live system you want this partition to mount to.

So in his tutorial he has a step where you mount the second partition and give the command:
<code>echo / union &gt; persistence.conf</code>
into the root of where you mounted partition 2. But what we need to do is take our 3rd partition, mount it to another location, CD into it and give the command:
<code>echo '/home' &gt;&gt; persistence.conf</code>

and now when you reboot into the live usb system, all three partitions will auto-mount, with sdb3 mounted on /home, when it finally worked for me, I showed ~9 GB more space in /home than I had previously.

So in summary, if you have a USB key and you want to run Debian-Live with (for some crazy reason) 10 partitions you want to mount persitently, each one must be labeled 'peristence" and each one needs to have persistent.conf in its /, that explains to Debian-Live where it will be mounted.

Please remember that blank spaces and the standard unix directory symbols ./ and ../ cannot be used in the persistence.conf file.

Also, please remember that Debian-Live ships with a default username and password pre-set,

User = 'user'

password = 'live'

so <strong>DON'T FORGET TO CHANGE YOUR PASSWORD</strong> by issuing the password command:
<code>passwd</code>

if you do not, and someone knows you are running Debian-Live, even just temporarily, they can get root access to your computer very easily. Change your password, because there is no point in running a persistent live Linux system if it doesn't have basic security.

&nbsp;

</div>
<div class="section" title="7.5.3. Snapshots"></div>
