---
id: 553
title: Laravel 5 quick tips
date: 2015-08-18T15:19:48+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=553
permalink: /2015/08/18/laravel-5-quick-tips/
categories:
  - Laravel
tags:
  - active class
  - laravel 5
---
Quick tip on setting an active class on a nav menu.

<pre>{{ Request::is('/') ? 'active' : '' }}</pre>