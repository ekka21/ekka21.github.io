---
id: 152
title: 'Selector &#038; Inheritance in SASS'
date: 2012-11-13T03:32:40+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=152
permalink: /2012/11/13/selector-inheritance-in-sass/
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
  - 10151182213999565
fb_status_messages:
  - 'a:1:{i:0;a:2:{s:7:"message";s:104:"Posted to <a href="http://www.facebook.com/10151182213999565" target="_blank">your Facebook Timeline</a>";s:5:"error";s:0:"";}}'
categories:
  - SASS
tags:
  - 'Selector &amp; Inheritance'
---
Look what I learn today inheritance selector in sass!

[code]
  
.box
  
margin: 0 auto 10px
  
border: 1px solid
  
padding: 15px
  
border-radius: 5px
  
.error
  
@extend .box
  
background-color: red
  
border-color: #ccc
  
.success
  
@extend .box
  
background-color: green
  
border-color: #ccc
  
<div class="box">Normal box</div>
  
<div class="important">Error</div>
  
<div class="success">Success</div>
  
[/code]