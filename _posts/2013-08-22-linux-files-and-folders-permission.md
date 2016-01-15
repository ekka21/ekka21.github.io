---
id: 349
title: Linux files and folders permission
date: 2013-08-22T15:16:07+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=349
permalink: /2013/08/22/linux-files-and-folders-permission/
categories:
  - Linux
tags:
  - groups
  - permissions
---
Making sure that any files or directories created inherited the www-data group

<pre>sudo usermod -a -G www-data USER_NAME
sudo chown -R www-data:www-data /var/www/vhosts
sudo chmod g+x /var/www/vhosts
</pre>