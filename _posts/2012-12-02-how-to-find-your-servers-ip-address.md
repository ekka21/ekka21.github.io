---
id: 197
title: How to Find your Server’s IP address
date: 2012-12-02T17:25:01+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=197
permalink: /2012/12/02/how-to-find-your-servers-ip-address/
categories:
  - Linux
tags:
  - ifconfig
---
<pre>ifconfig eth0 | grep inet | awk '{ print $2 }'
</pre>