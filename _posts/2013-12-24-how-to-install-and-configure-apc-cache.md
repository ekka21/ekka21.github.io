---
id: 366
title: How to install and configure APC cache
date: 2013-12-24T17:13:36+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=366
permalink: /2013/12/24/how-to-install-and-configure-apc-cache/
categories:
  - Linux
tags:
  - APC cache
  - cache
---
<pre>sudo aptitude install php-apc #Ubuntu
sudo yum install php-pecl-apc #RedHat, Centos or Fedora
</pre>

This is a suggested configuration for a box with 1Gb of RAM:

<pre>sudo vi /etc/php5/apache2/conf.d/apc.ini 
extension=apc.so
apc.enabled=1
apc.shm_size="128M"
apc.cache_by_default="1"
apc.shm_segments="1"
apc.ttl="7200"
apc.user_ttl="7200"
apc.gc_ttl="1800"
apc.optimization = 0
apc.num_files_hint="1024"
apc.use_request_time = 1
apc.mmap_file_mask="/tmp/apc.XXXXXX"
apc.enable_cli="0"
apc.slam_defense="0"
apc.file_update_protection="2"
apc.max_file_size="1M"
apc.stat="1"
apc.write_lock="1"
apc.report_autofilter="0"
apc.include_once_override="0"
apc.rfc1867="0"
apc.rfc1867_prefix="upload_"
apc.rfc1867_name="APC_UPLOAD_PROGRESS"
apc.rfc1867_freq="0"
apc.localcache="0"
apc.localcache.size="512"
apc.coredump_unmap="0"
apc.filters="composer"
</pre>

**Monitoring**

<pre>cp /usr/share/doc/php-apc/apc.php.gz /var/domains/sample.com/apc.php.gz
gunzip /var/domains/sample.com/apc.php.gz
</pre>

**Empty the cache manually?**
  
APC will be clear when you restart apache as well

<pre>touch apc-clear.php
vi apc-clear.php

if (in_array(@$_SERVER['REMOTE_ADDR'], array('127.0.0.1', '::1')))
{
  apc_clear_cache();
  apc_clear_cache('user');
  apc_clear_cache('opcode');
  echo json_encode(array('success' => true));
}
else
{
  die('SUPER TOP SECRET');
}
</pre>

Set up Corn job

<pre>0 6 * * * /usr/bin/curl --silent http://sample.com/apc-clear.php
</pre>