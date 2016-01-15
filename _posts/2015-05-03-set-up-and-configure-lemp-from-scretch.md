---
id: 502
title: Set up and configure LEMP from scretch
date: 2015-05-03T00:01:09+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=502
permalink: /2015/05/03/set-up-and-configure-lemp-from-scretch/
categories:
  - Linux
  - mysql
  - Nginx
  - php
  - Uncategorized
tags:
  - debian
  - lemp
  - mysql
  - nginx
  - php-fpm
  - ubuntu
---
This post is all about basic LEMP(Linux, Nginx, MySql and PHP) from the ground up. It is the traditional way to spin up the server, ssh in and manually install and configure everything from ground up.

By the end of this post, you should be able to have a full functioning LEMP server. Let&#8217;s do this!

### Getting a server from Digital Ocean

First thing first, you need a server. I have been using DigitalOcean as my hosting provider for 2-3 years now and I love their UI/UX and how simple it is to spin up the server. Here is my <a href="https://www.digitalocean.com/?refcode=c86ab6ba740f" target="_blank">Digital Ocean</a>. You will receive $10 in credit and I will get $25 credit in return. This is a win win situation! Once you sign up and add your credit card info, you are now ready to create your very first Droplet.

At the time of this post, I&#8217;m starting of as the minimal server so I pick my server spec as below:
  
&#8211; **Size**: $5 per month
  
&#8211; **Region**: Newyork
  
&#8211; **Image**: Ubuntu 14.04&#215;64

### Setup and configure the &#8220;L&#8221;

You should receive an email from Digital Ocean with your server credentials. Now heading over to your terminal and ssh in.

<pre>ssh root@SERVER_IP_ADDRESS</pre>

Let&#8217;s get the latest patched software to protect the server.

<pre>apt-get update</pre>

### Setup and configure the &#8220;E&#8221;

<pre>apt-get install nginx</pre>

Or if you want to make sure to get the latest version of Nginx

<pre>echo "deb http://ppa.launchpad.net/nginx/stable/ubuntu $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/nginx-stable.list
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C300EE8C
sudo apt-get update
sudo apt-get install nginx
</pre>

By default, Nginx will start after the install but if it doesn&#8217;t, you can start nginx yourself.

<pre>service nginx start</pre>

Now that you have Nginx up and running by browsing to your browser(http://SERVER\_IP\_ADDRESS), you probably want to know how to stop and/or restart eh?

<pre>service nginx stop</pre>

<pre>service nginx restart</pre>

<pre>service nginx reload</pre>

### Install and configure the &#8220;M&#8221;

To install MySql, type these commands. During the installation, MySql will ask you to set a root password so do it!

<pre>apt-get install mysql-server php5-mysql</pre>

<pre>sudo mysql_install_db
/usr/bin/mysql_secure_installation
</pre>

### Install and configure the &#8220;P&#8221;

Last but not least, the &#8220;P&#8221;!

<pre>apt-get install php5-fpm</pre>

Open up php.ini

<pre>vi /etc/php5/fpm/php.ini</pre>

Need to change cgi.fix\_pathinfo=1 to cgi.fix\_pathinfo=0 in php.ini.
  
This is for the security reason. If this number is set to 0, the interpreter will process the exact file path.

Restart php-fpm

<pre>service php5-fpm restart</pre>

Update nginx config

<pre>vi /etc/nginx/sites-available/default</pre>

Add these line of code in your default site.

<pre>server {
        listen   80;


        root /var/www/domains/default;
        index index.php index.html index.htm;

        server_name example.com;

        location / {
                try_files $uri $uri/ /index.html;
        }

        error_page 404 /404.html;

        error_page 500 502 503 504 /50x.html;
        location = /50x.html {
              root /var/www/domains/default;
        }

        # pass the PHP scripts to FastCGI server listening on the php-fpm socket
        location ~ \.php$ {
                try_files $uri =404;
                fastcgi_pass unix:/var/run/php5-fpm.sock;
                fastcgi_index index.php;
                fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
                include fastcgi_params;

        }

}
</pre>

Create your first working directory

<pre>mkdir -p /var/www/domains/ &#038;&#038; touch /var/www/domains/default
vi /var/www/domains/default
</pre>

Update default with the code below

<pre>phpinfo(); </pre>

Done!