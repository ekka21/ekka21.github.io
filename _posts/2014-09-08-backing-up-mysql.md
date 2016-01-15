---
id: 418
title: Backing up MySql
date: 2014-09-08T15:06:49+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=418
permalink: /2014/09/08/backing-up-mysql/
categories:
  - mysql
tags:
  - backup
  - mysql
  - mysqldump
  - restore
---
**Backup**
  
Backup all databases

<pre>mysqldump -u root -p[root_password] --all-databases > /tmp/all-database.sql
</pre>

Backup a single database

<pre>mysqldump -u root -p[root_password] [database_name] > /tmp/dumpfilename.sql
</pre>

Backup a single database and compressed it to a .gz

<pre>mysqldump -u root -p [root_password] [database_name] | gzip -9 > /tmp/dumpfilename-$(date +%d-%m-%Y).sql.gz
</pre>

Backup multiple databases

<pre>mysqldump -u root -p[root_password] --databases [database_name_1] [database_name_2] > /tmp/dumpfilename.sql
</pre>

Verify the dumpfilename.sql dump file contains both the database backup.

<pre>grep -i "Current database:" /tmp/dumpfilename.sql</pre>

Backup a specific table

<pre>mysqldump -u root -p[root_password] [database_name] [table_name] > /tmp/dumpfilename_with_specific_table.sql
</pre>

**Restore**

<pre>mysql -u root -p[root_password] [database_name] &lt; dumpfilename.sql</pre>

To restore compressed backup files:

<pre>gunzip &lt; [backupfile.sql.gz] | mysql -u [uname] -p[pass] [dbname]</pre>