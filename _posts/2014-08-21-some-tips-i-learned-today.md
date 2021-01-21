---
layout: post
title: Some Tips I learned Today
date: 2014-08-21 17:22
author: woh3
comments: true
categories: [FreeBSD, FreeBSD, Life, Quaker, Vegan, Vegan]
---
<p>when doing Vegan Baking, and you want to do a vegan substitute for eggs, you use 1 Ripe Banana (LARGE) for each egg in the recipe. I tried this before using small bananas and it came out of the oven as a brick. But using the large bananas made it come out perfect and wonderfully fluffy. My first attempt at Vegan Oatmeal Cookies were delicious, but a little harder than I would have liked, now that I know to use extra banana, I can't wait to try them again.</p><p>Also...<br /> when mounting an (external) usb drive in FreeBSD 10.0 the ordinary 'mount' command does not work, instead, try</p><p>'mount_msdosfs /dev/da? /mnt/usb/whatever'</p><p>where the ? is an integer of your device, usually 0.<br /> If you don't know the node of your device...try</p><p>gpart show da0</p><p>or</p><p>file -s /dev/da*</p><p>or you can even plug your device in, then type</p><p>dmesg | tail</p><p>where | is the 'pipe' symbol, in different places on keyboards but usually on the same key as  often under the backspace key.</p>
