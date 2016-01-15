---
id: 199
title: How to add a new user to mysql
date: 2012-12-02T17:48:13+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=199
permalink: /2012/12/02/how-to-add-a-new-user-to-mysql/
categories:
  - Linux
tags:
  - add a mysql new user
---
For creating a new user with all privileges (use only for troubleshooting), at mysql prompt type:

<pre>mysql -u root -p 
GRANT ALL PRIVILEGES ON *.* TO 'yourusername'@'localhost' IDENTIFIED BY 'yourpassword' WITH GRANT OPTION;</pre>

For creating a new user with fewer privileges (should work for most web applications) which can only use the database named &#8220;database1&#8243;, at mysql prompt type:

<pre>GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, INDEX, ALTER, CREATE TEMPORARY TABLES, LOCK TABLES ON database1.* TO 'yourusername'@'localhost' IDENTIFIED BY 'yourpassword';</pre>