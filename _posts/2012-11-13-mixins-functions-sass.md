---
id: 158
title: Functions SASS
date: 2012-11-13T04:05:36+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=158
permalink: /2012/11/13/mixins-functions-sass/
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
  - 10151182254609565
fb_status_messages:
  - 'a:1:{i:0;a:2:{s:7:"message";s:104:"Posted to <a href="http://www.facebook.com/10151182254609565" target="_blank">your Facebook Timeline</a>";s:5:"error";s:0:"";}}'
categories:
  - SASS
tags:
  - 'Mixins &amp; Functions'
---
Full lists of sass function can be found here
  
<a href="http://sass-lang.com/docs/yardoc/Sass/Script/Functions.html  " target="_blank">http://sass-lang.com/docs/yardoc/Sass/Script/Functions.html</a>

[code]

$red = red;

@function border\_color($in\_val){

@return desaturate( darken( $in_val, 25%) , 50%);

}

.box{

padding: 30px

border: 1px solid border_color($red);

}

[/code]