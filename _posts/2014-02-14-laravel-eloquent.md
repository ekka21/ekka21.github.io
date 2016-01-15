---
id: 382
title: Laravel Eloquent
date: 2014-02-14T18:09:41+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=382
permalink: /2014/02/14/laravel-eloquent/
categories:
  - Laravel
tags:
  - Eloquent
  - fetch
---
<pre>Model::orderBy('id', 'desc')->paginate(10);
</pre>

<pre>$field = array('field1','field2');
Model::orderBy('id', 'desc')->get($fields)->toArray();
</pre>