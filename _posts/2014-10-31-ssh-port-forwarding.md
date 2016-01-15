---
id: 430
title: SSH port forwarding
date: 2014-10-31T23:54:21+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=430
permalink: /2014/10/31/ssh-port-forwarding/
categories:
  - Linux
  - 'Tips &amp; Tricks'
tags:
  - port forwarding
  - ssh
  - tunnel
---
This is an ideal when you are trying testing your server on a different port. It can be done by using ssh -L forwarding port number

<pre>sudo ssh -L 80:IP-ADDRESS:8081 USER@IP-ADDRESS
</pre>

Don&#8217;t forget to set your site to that
  
127.0.0.1 your-site.com