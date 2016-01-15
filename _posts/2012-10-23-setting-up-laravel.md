---
id: 112
title: Setting up Laravel
date: 2012-10-23T18:37:04+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=112
permalink: /2012/10/23/setting-up-laravel/
fb_mentioned_pages:
  - 'a:0:{}'
fb_mentioned_pages_message:
  - 
fb_mentioned_friends:
  - 'a:0:{}'
fb_mentioned_friends_message:
  - 
fb_author_message:
  - 
fb_author_post_id:
  - 10151153116609565
fb_status_messages:
  - 'a:1:{i:0;a:2:{s:7:"message";s:104:"Posted to <a href="http://www.facebook.com/10151153116609565" target="_blank">your Facebook Timeline</a>";s:5:"error";s:0:"";}}'
fb_social_plugin_settings_box_like:
  - default
categories:
  - Laravel
tags:
  - laravel
  - laravel app config
  - laravel basic setting
---
4 steps to get Laravel framework up and running&#8230;

  * **Setup vhost** entry- root directory need to point to public in my vhosts setting would be something link below:

[code]
  
<VirtualHost *:80>
  
\# Admin email, Server Name (domain name) and any aliases
   
ServerAdmin me@localhost.com
   
ServerName xyz.com
   
ServerAlias www.xyz.com
   
ServerAlias qa.xyz.com
   
ServerAlias dev.xyz.com
   
ServerAlias local.xyz.com

\# Index file and Document Root (where the public files are located)
   
DirectoryIndex index.php
   
DocumentRoot /var/www/vhosts/xya.com/htdocs/public

<Directory /var/www/vhosts/xyz.com/htdocs/public>
   
Options -Indexes ExecCGI FollowSymLinks
   
AllowOverride All
   
</Directory>

\# Custom log file locations
   
LogLevel warn
   
ErrorLog /var/www/vhosts/xyz.com/logs/error.log
   
CustomLog /var/www/vhosts/xyz.com/logs/access.log combined

</VirtualHost>
  
[/code]

  * **Change storage directory permission**

[code]chmod -R 775 storage [/code]

  * Remove application.php **key**
  * Generate new key automatically!

[code]php artisan key:generate[/code]

  * Done!