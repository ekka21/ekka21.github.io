---
id: 487
title: Increase file upload size in Nginx globally
date: 2015-02-19T17:30:15+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=487
permalink: /2015/02/19/increase-file-upload-size-in-nginx-globally/
categories:
  - Linux
  - Nginx
  - php
  - Wordpress
tags:
  - filesize
  - fileupload
  - increase file size
  - nginx
---
Update PHP.ini

<pre>sudo vi /etc/php5/fpm/php.ini #or wherever your php.ini is
</pre>

Set the value to

<pre>upload_max_filesize = 8M
post_max_size = 10M
</pre>

This is just a common sense that post\_max\_size should always be larger than upload\_max\_filesize.

Change in Nginx config per site

<pre>http {
	#...
        client_max_body_size 10m;
	#...
}
</pre>

Restart php and nginx

<pre>sudo service php5-fpm reload
sudo nginx -t && sudo service nginx reload
</pre>