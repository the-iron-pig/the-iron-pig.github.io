---
layout: post
title: Communications Link Failure Error
date: 2010-01-11 07:47
author: woh3
comments: true
categories: [Linux, Slackware]
---
When trying to connect to a mysql database using oracles sqldeveloper on a slackware64 13.0 system, you will keep getting an error read "Communications Link failure" when trying to connect. This is due to a security setting in /etc/rc.d/rc.mysqld, do a search on this file for "skip-networking" and you will come to a paragraph, now the weird thing about Slackware here is that you need to comment out this line in order to enable it, it seems kind of backwards. Once I did this, I had a perfect connection to Mysql via Oracles Sqldeveloper
