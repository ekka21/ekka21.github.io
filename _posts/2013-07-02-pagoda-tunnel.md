---
id: 335
title: Pagoda tunnel
date: 2013-07-02T19:15:01+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=335
permalink: /2013/07/02/pagoda-tunnel/
categories:
  - Laravel
tags:
  - pagoda tunnel
---
Check what apps available

<pre>pagoda list</pre>

To update pagoda DB accounts

<pre>vi ~/.pagodarc</pre>

Create a tunnel to Pagoda Cloud db

<pre>pagoda tunnel -c db1</pre>

After that you can just use your normal sql client tool, for me is Sequel Pro

<pre>Host: localhost or 127.0.0.1
Username: from pagoda dashboard
Password: from pagoda dashboard
Port: 3307</pre>