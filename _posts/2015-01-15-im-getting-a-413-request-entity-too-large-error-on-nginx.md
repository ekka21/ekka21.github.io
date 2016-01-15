---
id: 481
title: 'I&#8217;m getting a 413 Request Entity Too Large error on NGINX'
date: 2015-01-15T17:29:34+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=481
permalink: /2015/01/15/im-getting-a-413-request-entity-too-large-error-on-nginx/
categories:
  - Linux
  - Nginx
  - php
tags:
  - client_max_body_size
  - nginx
---
You need to increase the size limit in nginx.conf or in your domain.com.conf. Add ‘client\_max\_body_size xxM’ inside the server section, where xx is the size (in megabytes) that you want to allow.

<pre>http {
    include       mime.types;
    default_type  application/octet-stream;
    sendfile        on;
    keepalive_timeout  65;

    server {
        client_max_body_size 20M;
        listen       80;
        server_name  localhost;

        # Main location
        location / {
            proxy_pass         http://127.0.0.1:8000/;
        }
    }
}
</pre>