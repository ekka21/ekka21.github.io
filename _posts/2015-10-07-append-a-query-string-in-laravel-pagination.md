---
id: 584
title: Append a query string in Laravel pagination
date: 2015-10-07T17:01:40+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=584
permalink: /2015/10/07/append-a-query-string-in-laravel-pagination/
categories:
  - Linux
  - php
tags:
  - laravel
  - pagination
---
This is how to append a GET variable into a pagination in >= Laravel 4.2

<pre>$users = User::all()-&gt;paginate(10);
return view('users.index', compact($users));
</pre>

In your view/users/index.blade.php

<pre>{{ $users-&gt;appends(['catId' =&gt; Input::get('catId'), 'statusId' =&gt; Input::get('statusId')])-&gt;render() }}
</pre>