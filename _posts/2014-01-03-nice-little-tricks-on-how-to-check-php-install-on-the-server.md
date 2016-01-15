---
id: 370
title: Nice little tricks on how to check PHP install on the server
date: 2014-01-03T18:59:40+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=370
permalink: /2014/01/03/nice-little-tricks-on-how-to-check-php-install-on-the-server/
categories:
  - Linux
  - php
tags:
  - phpinfo
---
<pre>which php
php --version
</pre>

To check php libs that are installed on your server

<pre>php -m
</pre>

To locate php.ini

<pre>php --init
</pre>