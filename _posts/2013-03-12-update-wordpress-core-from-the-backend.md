---
id: 286
title: Update wordpress core from the backend.
date: 2013-03-12T19:14:35+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=286
permalink: /2013/03/12/update-wordpress-core-from-the-backend/
categories:
  - 'Tips &amp; Tricks'
  - Wordpress
tags:
  - plugin
  - update wordpress core
  - updating core
  - wordpress
---
If you &#8216;ve ever had a problem updating WordPress Core or plugins from your backend. You are more likely having file permission issue. This can be vary but the solution below works for me like a charm!

<pre>define('FS_METHOD', 'direct');</pre>

Change Directories to 775 Permissions – Do this from the web root directory

<pre>sudo find . -type d -exec chmod 775 {} \;</pre>

Change Files Permissions to 664 – Do this from the htdocs folder.

<pre>sudo find . -type f -exec chmod 664 {} \;</pre>

Thanks to <a href="http://seansasso.com/" target="_blank">Sean Sasso</a>