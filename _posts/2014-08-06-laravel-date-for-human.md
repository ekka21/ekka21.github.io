---
id: 407
title: Laravel date for Human
date: 2014-08-06T20:50:15+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=407
permalink: /2014/08/06/laravel-date-for-human/
categories:
  - Laravel
tags:
  - create_at
  - date
---
<pre>$user = User::first();
echo $user->created_at->diffForHumans(); // 2 days ago

$user->touch();
echo $user->created_at->diffForHumans(); // a second ago
</pre>