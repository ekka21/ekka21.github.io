---
id: 254
title: How to add a user on Linux
date: 2013-02-08T16:39:24+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=254
permalink: /2013/02/08/how-to-add-a-user-on-linux/
categories:
  - Linux
tags:
  - add user linux
  - linux
  - redhat
---
To create a new admin user on a Linux system, use these commands:

<pre>sudo adduser -d /home/USERNAME -m USERNAME 
sudo passwd USERNAME
sudo chown -R  /home/USERNAME
sudo usermod -G wheel,apache USERNAME #wheel is admin group for Redhat/Centos
sudo passwd USERNAME</pre>

To create a new non-admin dev user, user this instead:

<pre>sudo adduser -d /home/USERNAME -m USERNAME
sudo passwd USERNAME
sudo chown -R  /home/USERNAME
sudo usermod -G dev,apache USERNAME
sudo passwd USERNAME</pre>