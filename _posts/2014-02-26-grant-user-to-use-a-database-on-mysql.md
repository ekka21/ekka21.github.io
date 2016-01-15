---
id: 387
title: Grant user to use a database on MySQL
date: 2014-02-26T20:26:10+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=387
permalink: /2014/02/26/grant-user-to-use-a-database-on-mysql/
categories:
  - mysql
tags:
  - grant
  - mysql
  - priviledge
---
(%) indicates connections which use the local socket;

<pre>mysql&gt; grant all on DB_NAME.* to 'backoffice_user'@'%';
</pre>

&#8220;localhost&#8221; indicates connections which originate on the local system but use the loopback network interface to connect;

<pre>mysql&gt; grant all on DB_NAME.* to 'backoffice_user'@'localhost';
</pre>

&#8220;SERVER\_NAME\_or\_IP\_ADDRESS&#8221;, refers to connections which originate elsewhere on the network.

<pre>mysql&gt; grant all on DB_NAME.* to 'USER_NAME'@'SERVER_NAME_or_IP_ADDRESS';
</pre>

You can also

<pre>"identified by password 'password-goes-here'"</pre>

on the end of the command.

<pre>grant SELECT, INSERT, UPDATE, DELETE, CREATE ON DB_NAME.* TO DB_USERNAME@'LOCALHOST' IDENTIFIED BY 'PASSWORD_GOES_HERE';</pre>