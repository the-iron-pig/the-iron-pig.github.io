---
layout: post
title: How to fix the error message in MySQL in Slackware 12.2
date: 2009-02-13 19:50
author: woh3
comments: true
categories: [Linux, Slackware]
---
For some reason there is a read/write permission conflict for /var/lib/mysql in a new slackware 12.2 install, which causes a "mysql has ended" error, you can remedy the error by chowning the directory. Usually to create the directory you need to run the command

mysql_install_db

then chown it with the command:

chown -R mysql:mysql /var/lib/mysql

then restart the server with the command

mysqld_safe &amp;

that should fix your problems, follow the rest of the instructions that appeared on your screen when you typed 'mysql_install_db' such as changing password etc, and you will be golden.
