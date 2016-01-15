---
id: 176
title: Setting up SMTP on Ubuntu Server
date: 2012-11-15T02:18:38+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=176
permalink: /2012/11/15/setting-up-smtp-on-ubuntu-server/
fb_social_plugin_settings_box_like:
  - default
fb_author_message:
  - 
fb_status_messages:
  - 'a:0:{}'
categories:
  - Linux
tags:
  - mail
  - postfix
  - smtp
---
<pre>sudo apt-get install postfix
sudo touch etc/php5/conf.d/mailconfig.ini
</pre>

Then add these line in mailconfig.ini

<pre>sendmail_from = me@example.com
sendmail_path = /usr/sbin/sendmail -t -i -f me@example.com
</pre>

Lastly, restart postfix service.

<pre>sudo /etc/init.d/postfix start
</pre>