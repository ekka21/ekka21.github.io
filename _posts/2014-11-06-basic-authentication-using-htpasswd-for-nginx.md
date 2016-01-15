---
id: 433
title: Basic authentication using .htpasswd for Nginx
date: 2014-11-06T15:32:45+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=433
permalink: /2014/11/06/basic-authentication-using-htpasswd-for-nginx/
categories:
  - Linux
  - Nginx
tags:
  - auth_basic
  - htpasswd
  - nginx
  - password
---
<pre>location / {
        try_files $uri $uri/ /index.php?$query_string;

        auth_basic            "Restricted Area";
        auth_basic_user_file  /var/www/domainname.com/folder/.htpasswd;
    }
</pre>