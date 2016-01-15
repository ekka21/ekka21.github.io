---
id: 75
title: Site offline for maintenance
date: 2012-10-11T13:19:18+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=75
permalink: /2012/10/11/site-offline-for-maintenance/
categories:
  - 'Tips &amp; Tricks'
  - Wordpress
tags:
  - maintenance
  - offline
---
From time to time I want to log down the WordPress backend from Users who update the content in the backend.
  
Just add this code in **Functions.php**

<pre>function wp_ob_backend_offline() {
 if ( is_admin() )
 {
 wp_die( '&lt;strong&gt;Site offline for maintenance!&lt;/strong&gt;
Hang on - we´ll be right back online!', 'Site Offline For Maintenance', '');
 }
}

add_action('init', 'wp_ob_backend_offline');
</pre>