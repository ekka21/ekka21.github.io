---
id: 291
title: Setting up Laravel 4
date: 2013-03-25T17:48:47+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=291
permalink: /2013/03/25/setting-up-laravel-4/
categories:
  - Laravel
  - Uncategorized
tags:
  - l4
  - laravel 4
---
First of you will need to <a href="http://getcomposer.org/doc/00-intro.md#globally" target="_blank">install Composer</a>.

<pre>composer create-project laravel/laravel MY_APP_NAME
chmod -R 777 app/storage
git init
git add .
git commit -m 'first init'</pre>

Now that&#8217;s the way to install a framework should be&#8230;.way to go Tarlor Otwell!

At this point you are almost ready to go but you just need to point your application root to public folder. In my case my web root of this application is path/to/MY\_APP\_NAME/public.

Done. Now let &#8216;s get to work&#8230;happy coding!