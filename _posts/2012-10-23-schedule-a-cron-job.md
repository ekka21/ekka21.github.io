---
id: 109
title: Schedule a cron job
date: 2012-10-23T13:40:18+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=109
permalink: /2012/10/23/schedule-a-cron-job/
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
  - 10151152764709565
fb_status_messages:
  - 'a:1:{i:0;a:2:{s:7:"message";s:104:"Posted to <a href="http://www.facebook.com/10151152764709565" target="_blank">your Facebook Timeline</a>";s:5:"error";s:0:"";}}'
categories:
  - Linux
tags:
  - cron
  - crontab
---
Show all on the tasks

<pre>crontab -l</pre>

Add/Edit tasks, after you exit from the editor, the modified crontab will be installed automatically.

<pre>crontab -e</pre>

How to schedule the tasks?

<pre># For details see man 4 crontabs

# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  *  command to be executed
  10 13 *  *  *  php PATH/my_script.php 
</pre>

This example will run everyday at 1.10pm.

References: <a href="http://www.thegeekstuff.com/2009/06/15-practical-crontab-examples/" target="_blank">http://www.thegeekstuff.com/2009/06/15-practical-crontab-examples/</a>

Enjoy!