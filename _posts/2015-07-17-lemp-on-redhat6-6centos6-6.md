---
id: 538
title: LEMP on Redhat6.6/Centos6.6
date: 2015-07-17T21:36:53+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=538
permalink: /2015/07/17/lemp-on-redhat6-6centos6-6/
categories:
  - Linux
  - mysql
  - Nginx
tags:
  - centos
  - lemp
  - php-fpm
  - redhat
---
Install packages from Webtatic.

<pre>sudo rpm -Uvh https://mirror.webtatic.com/yum/el6/latest.rpm</pre>

Install Nginx 1.8

<pre>sudo yum install nginx18</pre>

<pre>sudo service nginx start</pre>

Install PHP5.6

<pre>sudo yum install php56w-common php56w-fpm php56w-cli php56w-mbstring php56w-gd php56w-mcrypt php56w-pdo php56w-mysql php56w-xml php56w-xmlrpc php56w-pear php56w-pecl-imagick php56w-pecl-apcu</pre>

Change cgi.fix\_pathinfo=1 to cgi.fix\_pathinfo=0

<pre>sudo vi /etc/php.ini</pre>

Update

<pre>sudo vi /etc/php-fpm.d/www.conf</pre>

Replace the apache in the user and group with nginx

<pre>[...]
; Unix user/group of processes
; Note: The user is mandatory. If the group is not set, the default user's group
;	will be used.
; RPM: apache Choosed to be able to access some dir as httpd
user = nginx
; RPM: Keep a group allowed to write in log dir.
group = nginx
[...]
</pre>

Start up php-fpm

<pre>sudo service php-fpm restart
</pre>

Install MySql5.5

<pre>sudo yum install mysql-libs yum-plugin-replace
sudo yum replace mysql-libs –replace-with mysql55w-libs
sudo yum install mysql55w-server
sudo service mysqld start
sudo /usr/bin/mysql_secure_installation
</pre>

Setup auto start

<pre>sudo chkconfig --levels 235 mysqld on
sudo chkconfig --levels 235 nginx on
sudo chkconfig --levels 235 php-fpm on
</pre>

*References:

&#8211; <a href="https://webtatic.com/packages/nginx18/" target="_blank">Webtatic Nginx</a>
  
&#8211; <a href="https://webtatic.com/packages/php56/" target="_blank">Webtatic PHP5.6</a>