---
id: 441
title: Add a new /etc/hosts shell script
date: 2014-11-28T22:14:00+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=441
permalink: /2014/11/28/add-a-new-etchosts-shell-script/
categories:
  - Linux
  - 'Tips &amp; Tricks'
  - Vim
tags:
  - etchosts
  - hosts
---
As a web developer, I have to edit /etc/hosts daily. Even though I use Vi to update the file and I usually can get it done quickly enough(usually 20 seconds) but 20 seconds for just adding a /etc/host is way too long for me. So I wrote a little shell script to speed up the process a little bit. 

## Installation
  


## Copy the script to your machine

<pre>curl -L http://bit.ly/1FD5aWv > addhost
or 
wget -O addhost http://bit.ly/1FD5aWv
</pre>

Make the script to be executable and move to bin folder so you can use it globally

<pre>chmod +x addhost &#038;&#038; mv addhost /usr/local/bin/addhost
</pre>

How to use it?
  


Enjoy!