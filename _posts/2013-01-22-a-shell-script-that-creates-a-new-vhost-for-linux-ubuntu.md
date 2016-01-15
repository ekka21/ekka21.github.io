---
id: 240
title: A shell script that creates a new vhost for Linux Ubuntu
date: 2013-01-22T23:12:21+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=240
permalink: /2013/01/22/a-shell-script-that-creates-a-new-vhost-for-linux-ubuntu/
categories:
  - Uncategorized
---
Whenever I want to setup a new vhost on my server(Linux Ubuntu), I always do it manually. It&#8217;s not that bad but it really gets on my nerve if I have to do it more than 2-3 site everyday or month.

After do a little research how to automate this process, it&#8217;s actually quite easy. Here&#8217;s how:

You will need to create a shell script on your server. I actually create a repo on github, you can clone it from <a href="https://github.com/ekka21/ubuntu-add-vhost" target="_blank">here</a> .

Login & go to your home directory

<pre>git clone git@github.com:ekka21/ubuntu-add-vhost.git shell</pre>

Once you have it on  server, this script needs to be executable.

<pre>cd shell; chmod +x vhost.sh;</pre>

How to use it?&#8230;

<pre>sudo ./vhost.sh</pre>

After that you just need to follow the command prompt

This script cuts down about 10-20mins of your time, so you can concentrate on what you do best&#8230;CODING!