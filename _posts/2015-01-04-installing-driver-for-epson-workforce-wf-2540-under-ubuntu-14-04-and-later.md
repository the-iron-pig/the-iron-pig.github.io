---
layout: post
title: Installing Driver for Epson Workforce WF-2540 under Ubuntu 14.04 and later
date: 2015-01-04 16:35
author: woh3
comments: true
categories: [Linux, Ubuntu]
---
The Epson WF-2540 is a great little printer and not very difficult to setup under Ubuntu 14.04 and later. It doesn't work straight out of the box, if you use Ubuntu's Add Printer Dialogue it suggests Generic Drivers that seem to setup fine, but do not work when it comes to printing test pages (in fact, in one iteration of my efforts the test page came out with a message "<em>if you can read this you are using the wrong driver</em>" ?!?!). 
So, it turns out Epson actually has a Linux Driver that they supply to you, which can be freely downloaded from their website. But before that driver will work, you will need <strong>LPR</strong> installed on your system:
<code><pre>sudo apt-get install lpr</pre></code>
installing that will also install a buttload of dependencies, when that is all done, you will be able to install the epson driver via website and pkg manager:
go to:
<code><pre>http://download.ebz.epson.net/dsc/search/01/search/?OSC=LX</pre></code>
and type in WF-2540 (or another epson model) and it will take you to the download page, you must click "accept" and once you do, the web page will suddenly update and become 'longer' with a new table that has various versions and formats of the driver, I was using an i386, so I downloaded the epson-inkjet-printer-escpr_1.4.4-1lsb3.2_i386.deb (remember Ubuntu prefers the .deb. format for its packages) and then when it starts to download, there should be a download dialogue option for "open with" and ubuntu package manager should automatically be selected. If not, then you can go into the directory where you downloaded it and double click the package, it should pop open with package manager and install. If you prefer to do it by command line instead, you can do:
<code><pre>sudo apt-get install epson-inkjet-printer-escpr</pre></code>
Once all that is installed, THEN redo the Add Printer dialogue in "settings" (if a previous install of this printer is still on your system from before, right click the printer and Delete it) it should now proceed much more quickly, and find what it needs on its own, and you will be taken to the "Print Test Page" button. Hit it, and see the printing of nice words and colors and shapes. 
