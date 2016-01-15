---
id: 677
title: Adding http not found error handler in Laravel 5
date: 2016-01-07T17:28:03+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=677
permalink: /2016/01/07/adding-http-not-found-error-handler-in-laravel-5/
dsq_needs_sync:
  - 1
categories:
  - Laravel
tags:
  - http not found
  - laravel
---
In app\Exceptions\handler.php, add below:

<pre>if($e instanceof \Symfony\Component\HttpKernel\Exception\NotFoundHttpException)
    {
        // some code
    }
</pre>