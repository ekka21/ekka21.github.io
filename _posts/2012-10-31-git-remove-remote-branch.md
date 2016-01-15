---
id: 135
title: Git remove branch
date: 2012-10-31T15:15:43+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=135
permalink: /2012/10/31/git-remove-remote-branch/
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
  - 10151164254794565
fb_status_messages:
  - 'a:1:{i:0;a:2:{s:7:"message";s:104:"Posted to <a href="http://www.facebook.com/10151164254794565" target="_blank">your Facebook Timeline</a>";s:5:"error";s:0:"";}}'
categories:
  - Git
tags:
  - delete remote branch
  - git branch
---
Remove local branch

<pre>git branch -D BRANCH_NAME
</pre>

Remove remote branch

<pre>git push origin :BRANCH_NAME
</pre>

Delete all local branch except master

<pre>git branch | grep -v 'master' | xargs git branch -D
</pre>