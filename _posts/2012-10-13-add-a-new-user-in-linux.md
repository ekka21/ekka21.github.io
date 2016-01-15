---
id: 81
title: Add a new user in Linux Redhat
date: 2012-10-13T15:00:43+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=81
permalink: /2012/10/13/add-a-new-user-in-linux/
categories:
  - Linux
tags:
  - adduser
  - redhat
  - usermod
---
[code]adduser -d /home/USERNAME -m  USERNAME[/code]
  
-d  means  &#8212; The new user will be created using HOME_DIR as the value for the user´s login directory.
  
-m means &#8212; Create the user´s home directory if it does not exist.

[code]usermod -G group1, group2, group3 USERNAME[/code]
  
-G means &#8212; a list of supplementary groups which the user is also a member of.