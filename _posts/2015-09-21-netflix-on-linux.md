---
layout: post
title: Netflix on Linux
date: 2015-09-21 04:00
author: woh3
comments: true
categories: [Life]
---
It turns out getting Netflix on Linux is pretty easy. It requires Google Chrome. Not Chromium. Most linux distros ship with chromium native, but it turns out that chromium is missing a lot of the DRM plugins needed for Netflix, one important one being WideVine. I have tried to find source and compile Widevine for various distros, and it never really worked out well, but yay, the easy solution is download and install actual genuine <a href="https://www.google.com/chrome/browser/desktop/">Google-Chrome-Stable from google</a>. They have tons of packages, whether you run RPM distro or DEB distro or whatever else, and that package contains widevine native. I have tried it on Debian, and Ubuntu and openSUSE, each time I was watching Netflix within a few minutes. Hope this helps, i know it took me a long time to figure out that Chromium isn't actually Chrome. It is important to remember that once you install, you will likely have both Chromium and Chrome, so take note of which icon you are clicking, and if you are launching from command line, the command is not chromium, but rather:
<code>google-chrome-stable</code>
I like to include &amp; at the end of the command to free up the command line once it launches, otherwise your terminal will be occupied with errors and outputs from chrome, it still might show some, but you can just get the command prompt back by hitting enter again during the output from chrome.
