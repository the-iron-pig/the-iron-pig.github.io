---
layout: post
title: How to use Bittorrent Wisely.
date: 2013-03-28 17:53
author: woh3
comments: true
categories: [Fun, Life, Linux, Personal, Privacy, Security, Security, Slackware, Software Review, Ubuntu]
---
Over the years I have heard many horror stories about people getting notices from their IP service provider about being nailed for downloading "Tracked" torrents etc. One of the first steps in making sure this does not happen is shop around for IP Service providers, some of them respect your privacy much more than others. I once got a letter from my ISP complaining about my use of Bittorrent when I was using it to download Linux OS iso's, a perfectly legitimate use, but they regarded <strong>any</strong> use of Bittorrent to be <strong>infringement</strong>. I dropped them and went with a lesser known, slightly more pricey, but much more discrete service provider.

There are some things you can do to make sure that problems don't arise for you, and I am going to show some examples of such in this article. In this article my examples will be using the excellent BT program "Transmission", which is available for Windows, but you should be using Linux anyway.

<strong>Secure Connection:</strong>

One of the main things you need to be considering when you are about to use BT, is that when you go to a torrent index site, such as Piratebay, you need to make sure you have a secure connection...

<a href="http://woh3blog.files.wordpress.com/2013/03/google-secure.png"><img class="alignnone size-medium wp-image-832" alt="google-secure" src="http://woh3blog.files.wordpress.com/2013/03/google-secure.png?w=300" width="300" height="231" /></a>

Normally, when most people go to Google, they have a "Secure Connection" automatically, and you can see that in the picture above (I am using the Opera Browser in this picture) and that means that you are not connected to http://www.google.com, but rather you are connected to https://www.google.com, notice the "S" in the address, it stands for "Secure", which means your traffic with this site is encrypted. Many sites on the Internet offer a secure version of themselves, usually just add the extra S manually and reload and see if you connect, you might be surprised.

So below is a picture of a very common torrent index site viewed through an un-secure connection, the ordinary http protocol....

<a href="http://woh3blog.files.wordpress.com/2013/03/pb-unsecure.png"><img class="alignnone size-medium wp-image-833" alt="pb-unsecure" src="http://woh3blog.files.wordpress.com/2013/03/pb-unsecure.png?w=300" width="300" height="201" /></a>

and here is the secure version of PB....

<a href="http://woh3blog.files.wordpress.com/2013/03/pb-secure-2.png"><img class="alignnone size-medium wp-image-834" alt="pb-secure-2" src="http://woh3blog.files.wordpress.com/2013/03/pb-secure-2.png?w=300" width="300" height="209" /></a>

if and when you decide to go to a torrent index site, ALWAYS make sure you are using the HTTPS version of the site, this does not guarantee your safety, but it helps a lot. Update all your bookmarks of addresses to your index sites to the HTTPS versions, because in some places even looking at a known index site, or searching for things on them throws up red flags, so even if you are just browsing, use the Secure site.

<strong>Program Settings:</strong>

As I said, in this example I am using the BT program "<a href="http://www.transmissionbt.com/">Transmission</a>" , but most major torrent programs have very similar settings. Two of the most important privacy settings you can have in Transmission are your Blocklists and your Encryption settings, if you call up the preferences menu (under Edit---&gt;Preferences) you see this...

<a href="http://woh3blog.files.wordpress.com/2013/03/transmission-prefs.png"><img class="alignnone size-medium wp-image-835" alt="transmission-prefs" src="http://woh3blog.files.wordpress.com/2013/03/transmission-prefs.png?w=300" width="300" height="259" /></a>

and then go to the "Privacy" Tab...

<a href="http://woh3blog.files.wordpress.com/2013/03/transmission-privacy.png"><img class="alignnone size-medium wp-image-836" alt="transmission-privacy" src="http://woh3blog.files.wordpress.com/2013/03/transmission-privacy.png?w=300" width="300" height="253" /></a>

now there are several important details in this picture. When you first download Transmission and you go to this menu for the first time, you will have to tick the check box "Enable Blocklist" and the text field next to the check box will become active, asking you for an address of the blocklist publilsher, there are many blocklist publishers on the Internet, but the one I prefer (and is free) is <a href="http://www.iblocklist.com/list.php?list=bt_level1">iBlocklist</a> from bluetrack. Just google "BT Blocklist" and they will most likely be the top result, then while on their page, click some of your preferences as to the format of the list (usually the default settings will be fine) and copy and paste the web address they have posted in the text box on their site, and paste that address into the transmission blocklist address box you see in the pic above, then click "UPDATE", this is very important, if you do not update you won't be secure. After a few minutes it will say something like "Blocklist Contains 229,294 Rules" and that means you are now avoiding 229,294 bastards on the internet who might do things like share you an illegal file and report you, or whatnot.

Then go down to the lower part of the same tab, and you will see a drop down menu that has three options, "No Encryption", "Prefer Encryption" and "Require Encryption", I will give you three guesses about which one you want, but you won't need them. Set it to REQUIRED, this means both your upstream and downstream traffic with other BT users will be encrypted. This does not make you immune from getting busted, but it helps since it usually is not worth nosy service providers time to try to deal with encrypted packets. This means that you will be drawing from a somewhat smaller pool of seeders for certain files, but its the price you pay for security, and consider this, Studios who are trying to entrap you by offering you a copyrighted file will almost never encrypt their traffic, so it helps you to avoid the dreaded Honey-Pot trap.

Nothing is fool-proof nowadays, but I have found these above options to be very helpful in keeping my use of BT my business and no one else's. I hope it helps you too.
