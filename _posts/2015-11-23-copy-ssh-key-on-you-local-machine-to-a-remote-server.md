---
id: 661
title: Copy ssh key on you local machine to a remote server
date: 2015-11-23T17:16:19+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=661
permalink: /2015/11/23/copy-ssh-key-on-you-local-machine-to-a-remote-server/
categories:
  - Linux
tags:
  - ssh
  - ssh-copy-id
---
First generate you ssh key on your local machine

<pre>ssh-keygen -t rss</pre>

Install ssh-copy-id

<pre>sudo brew install ssh-copy-id</pre>

or 

<pre>sudo curl https://raw.githubusercontent.com/beautifulcode/ssh-copy-id-for-OSX/master/ssh-copy-id.sh -o /usr/local/bin/ssh-copy-id sudo chmod +x /usr/local/bin/ssh-copy-id
</pre>

Second, let&#8217;s copy the key to your remove server. 

<pre>ssh-copy-id -i ~/.ssh user@machine</pre>

References: <a href="http://www.jacobtomlinson.co.uk/2013/01/24/ssh-copy-id-os-x/" target="_blank">http://www.jacobtomlinson.co.uk/2013/01/24/ssh-copy-id-os-x/</a>
  
Done!