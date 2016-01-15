---
id: 354
title: Linux command to show traffic on a server
date: 2013-11-27T15:36:38+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=354
permalink: /2013/11/27/linux-command-to-show-traffic-on-a-server/
categories:
  - Linux
tags:
  - distro
---
This shows the active connections on port 80 right now / within the timeout parameter.

<pre>netstat -tupan | grep 80
or
netstat -a -n | grep :80 | cut -d : -f2 | awk '{print $2}' | sort | uniq -c | sort 
</pre>

Monitor open connections for httpd including listen, count and sort it per IP

<pre>watch "netstat -plan | grep -v LISTEN | grep \":80 \" | awk {'print \$5'} | cut -d: -f 1 | uniq -c | sort -nk 1"
</pre>

<pre>tail -50000 access_log | awk '{print $1}' | sort | uniq -c | sort -n | tail
</pre>

Check what linux distro you are running.

<pre>cat /etc/*-release</pre>