---
layout: post
title: How to get Amarok to recognize your MTP based mp3 player
date: 2009-03-08 19:48
author: woh3
comments: true
categories: [Linux]
---
in Amarok (1.*)
===&gt;Settings===&gt;Configure Amarok
Select "Media Devices" tab

do not click 'Autodetect Devices' instead click 'Add Devices'
you will get a new window

If your version of Amarok was compiled with MTP support (which is very likely) you will have a MTP device option in the dropdown menu, select it and give your device a name, like "My Zen" or something, save changes and you are done.

If you dont have MTP option in your dropdown then your amarok was not compiled with MTP support, so you need to re-compile it, and in the configure step you need to pass the configure script the additional argument --enable-mtp
