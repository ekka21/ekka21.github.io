---
id: 168
title: .htaccess redirect
date: 2012-11-13T18:09:41+00:00
author: ek
layout: post
guid: http://www.ekkachai.net/?p=168
permalink: /2012/11/13/htaccess-redirect/
fb_social_plugin_settings_box_like:
  - default
fb_author_message:
  - 
fb_status_messages:
  - 'a:0:{}'
categories:
  - Linux
tags:
  - .htaccess redirect
---
<pre>RewriteEngine on

# remove .php 
RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME}\.php -f
RewriteRule ^(.*)$ $1.php

# redirect www.domain2.com and domain2.com to domain.com
RewriteCond %{HTTP_HOST} ^www.domain2.com$ [OR]
RewriteCond %{HTTP_HOST} ^domain2.com$ [OR]

# redirect www.domain.com to domain.com
RewriteCond %{HTTP_HOST} ^www.domain.com$ 
RewriteRule (.*)$ http://domain.com/$1 [R=301,L]
</pre>