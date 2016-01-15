---
id: 164
title: Mixins SASS
date: 2012-11-13T04:20:56+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=164
permalink: /2012/11/13/mixins-sass/
fb_social_plugin_settings_box_like:
  - default
fb_mentioned_pages:
  - 'a:0:{}'
fb_mentioned_pages_message:
  - 
fb_mentioned_friends:
  - 'a:0:{}'
fb_mentioned_friends_message:
  - 
fb_author_message:
  - 
fb_author_post_id:
  - 10151182267124565
fb_status_messages:
  - 'a:1:{i:0;a:2:{s:7:"message";s:104:"Posted to <a href="http://www.facebook.com/10151182267124565" target="_blank">your Facebook Timeline</a>";s:5:"error";s:0:"";}}'
categories:
  - SASS
tags:
  - sass mixins
---
For me Mixin is your sass custom functions.

[code]

@mixin colored\_box($in\_val){

@extend .box

background-color: $in_val

border-color: border_color($color)

}

[/code]