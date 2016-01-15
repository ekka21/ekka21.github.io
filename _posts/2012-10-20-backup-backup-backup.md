---
id: 105
title: Backup Backup Backup!
date: 2012-10-20T13:57:20+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=105
permalink: /2012/10/20/backup-backup-backup/
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
  - 10151148518469565
fb_status_messages:
  - 'a:1:{i:0;a:2:{s:7:"message";s:104:"Posted to <a href="http://www.facebook.com/10151148518469565" target="_blank">your Facebook Timeline</a>";s:5:"error";s:0:"";}}'
categories:
  - Linux
tags:
  - mysqldump
---
This command will dump all databases, compress it and put in the destination path with timestamp

<pre>mysqldump -u USER -pPASSWORD --all-databases --dump-date | gzip &gt; /PATH/(date +%Y-%m-%d).sql.gz</pre>

How to unzip .gz?

<pre>gunzip FILENAME.sql.gz</pre>

Man, I feel a lot better when I know I have Backup.

<pre>backup: # mysqldump -u root -p[root_password] [database_name] &gt; dumpfilename.sql
restore:# mysql -u root -p[root_password] [database_name] &lt; dumpfilename.sql</pre>

config server time zone

<pre>sudo dpkg-reconfigure tzdata</pre>

Enjoy!