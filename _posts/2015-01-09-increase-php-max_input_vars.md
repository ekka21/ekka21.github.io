---
id: 476
title: Increase PHP max_input_vars
date: 2015-01-09T20:18:12+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=476
permalink: /2015/01/09/increase-php-max_input_vars/
categories:
  - Linux
  - php
tags:
  - max_input_vars
  - php
  - post_vars
---
If you have a really really long form POST, you might want to increase your php defualt from 1000 to 10000. Here is how.

Edit /etc/php5/fpm/php.ini
  
search max\_input\_vars = 1000
  
increase 1000 to 10000