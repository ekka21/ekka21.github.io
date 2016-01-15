---
id: 422
title: Url redirect for Nginx
date: 2014-10-02T17:42:10+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=422
permalink: /2014/10/02/url-redirect-for-nginx/
categories:
  - Nginx
tags:
  - .htaccess
  - nginx
  - redirect
---
<pre># For a single url
location = /old/path{
	return 301 http://foo.com/new/url
}

# For complete section - wildcard
location ~ /old/(.*){
	return 301 http://foo.com/new/$1
}
</pre>