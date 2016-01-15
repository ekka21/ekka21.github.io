---
id: 13
title: Post value sanitizing
date: 2012-10-02T14:59:40+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=13
permalink: /2012/10/02/post-value-sanitizing/
categories:
  - Wordpress
tags:
  - add_post_meta
  - escape
  - sanitizin
---
I found this bug in my code to day. It happens when I have &#8216; or &#8221; or / or \ in my input fields.

Use esc_attr() to escape all of those

Here is the fix&#8230;

[php]

add\_post\_meta(ID, "META\_KEY", esc\_attr($\_POST[first\_name]), true);

[/php]