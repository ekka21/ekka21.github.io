---
id: 305
title: php artisan problem
date: 2013-08-22T15:06:43+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=305
permalink: /2013/08/22/php-artisan-problem/
categories:
  - Laravel
tags:
  - artisan
  - l4
  - laravel
  - mcrypt
  - php artisan
---
I ran into a problem where I tried to use php artisan command when developing Laravel 4. The error message is &#8220;Laravel 4 is mCrypt&#8221;

<span style="line-height: 1.714285714; font-size: 1rem;">Here is the fix.</span>

<pre>#MAMP PHP
alias phpize='/Applications/MAMP/bin/php/php5.4.4/bin/phpize'
alias pear='/Applications/MAMP/bin/php/php5.4.4/bin/pear'
alias pecl='/Applications/MAMP/bin/php/php5.4.4/bin/pecl'
alias php='/Applications/MAMP/bin/php/php5.4.4/bin/php'</pre>