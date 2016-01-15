---
id: 202
title: Create the New Virtual Host File in Ubuntu
date: 2012-12-02T21:04:06+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=202
permalink: /2012/12/02/create-the-new-virtual-host-file-in-ubuntu/
categories:
  - Linux
tags:
  - add new host
  - apache
  - new host file
  - vhost
  - vhosts
---
Enable site

<pre>sudo cp /etc/apache2/sites-available/default /etc/apache2/sites-available/example.com
 sudo nano /etc/apache2/sites-available/example.com
 sudo a2ensite example.com
 sudo /etc/init.d/apache2 reload</pre>

Disable site

<pre># disable site
sudo a2dissite SITE_NAME

# enable an apache2 module
sudo a2enmod</pre>

Restarting apache

<pre>#check apache config file
apache2ctl -t

#restart
sudo /etc/init.d/apache2 restart</pre>