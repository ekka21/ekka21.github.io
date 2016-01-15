---
id: 213
title: Sync wordpress uploads folder the lazy way
date: 2012-12-11T21:08:19+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=213
permalink: /2012/12/11/sync-wordpress-uploads-folder-the-lazy-way/
categories:
  - Linux
tags:
  - rsync
---
Add this shell script to your ~/.bash_profile
  
*I assume that your vhost path is /var/www/vhost or you can change it to yours

<pre>function sync_down() 
{
rsync -avz USERNAME@SERVER:/var/www/vhosts/$1/htdocs/wp-content/uploads/* /var/www/vhosts/$1/htdocs/wp-content/uploads/
}

function sync_up() 
{
rsync -avz /var/www/vhosts/$1/htdocs/wp-content/uploads/* USER@SERVER:/var/www/vhosts/$1/htdocs/wp-content/uploads/
}</pre>

How to use it?

  * sync_down domainname.com
  * sync_up domainname.com

What can I say, I&#8217;m a lazy programmer! <img src="http://ekkachai.net/wp-includes/images/smilies/simple-smile.png" alt=":-)" class="wp-smiley" style="height: 1em; max-height: 1em;" />