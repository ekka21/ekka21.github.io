---
id: 351
title: Change WordPress table prefix the right way
date: 2013-08-23T20:28:09+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=351
permalink: /2013/08/23/change-wordpress-table-prefix-the-right-way/
categories:
  - Wordpress
tags:
  - prefix table name
  - wordpress
---
Adding a little more security to you WordPress site by changing wordpress prefix to something hacker will never guess&#8230;.
  
Here &#8216;s how&#8230;
  
Backup Backup Backup!

Open up wp-config.php and change

<pre>$table_prefix  = 'wp_';</pre>

to

<pre>$table_prefix  = 'PREFIX_';</pre>

Run these sql commands from your fav client SQL tool or phpmyadmin

<pre>RENAME table wp_commentmeta TO PREFIX_commentmeta;
RENAME table wp_comments TO PREFIX_comments;
RENAME table wp_links TO PREFIX_links;
RENAME table wp_options TO PREFIX_options;
RENAME table wp_postmeta TO PREFIX_postmeta;
RENAME table wp_posts TO PREFIX_posts;
RENAME table wp_term_relationships TO PREFIX_term_relationships;
RENAME table wp_term_taxonomy TO PREFIX_term_taxonomy;
RENAME table wp_terms TO PREFIX_terms;
RENAME table wp_usermeta TO PREFIX_usermeta;
RENAME table wp_users TO PREFIX_users;

UPDATE PREFIX_options SET option_name = REPLACE(option_name,'wp_','PREFIX__') WHERE option_name LIKE 'wp_%';

UPDATE PREFIX_usermeta SET meta_key = REPLACE(meta_key,'wp_','PREFIX_') WHERE meta_key LIKE 'wp_%';</pre>