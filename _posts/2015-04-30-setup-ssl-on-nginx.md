---
id: 495
title: Setup SSL on Nginx
date: 2015-04-30T17:16:07+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=495
permalink: /2015/04/30/setup-ssl-on-nginx/
categories:
  - Linux
  - Nginx
tags:
  - ssl
---
First thing you need to create CSR(Certificate Signing Request), so log in to your server.

<pre>openssl req -new -newkey rsa:2048 -nodes -keyout server.key -out DOMAINNAME.csr</pre>

Then you need to enter the information as needed.

Copy your DOMAINNAME.csr and paste it your your SSL registrar.

Then you have gotten to wait for your registrar to issue CPTs.

Once you have CPTs, you will need to add those file to your server. I usually put them at working directory under ssl (For example, /var/www/domains/xyz.com/ssl)

Configure your nginx ssl, usually it is located at /etc/nginx/sites-available/xyz.com.conf or wherever your is but my server is ubuntu.

Add this

<pre>server {
        listen          80;
        server_name     xyz.com;
        return  301  https://xyz.com$request_uri;
}

server {
        listen 443 ssl;
        servername xyz.com;
        
        location /{
             root /var/www/domains/xyz.com/htdocs;
             index  index.html index.htm index.php;
             try_files $uri $uri/ /index.php?$query_string;
        }

        ssl_certificate     /var/www/domains/xyz.com/ssl/xyz.com.crt;
        ssl_certificate_key /var/www/domains/xyz.com/ssl/xyz.com.key;
        ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
        ssl_ciphers ECDHE-RSA-AES128-GCM-SHA256:ECDHE-RSA-RC4-SHA:ECDHE-RSA-AES128-SHA:AES128-GCM-SHA256:RC4:HIGH:!EDH:!MD5:!aNULL:!SSLv2;

}
</pre>

Restart your webserver

<pre>sudo nginx -t && sudo service nginx reload</pre>

You are now having a secure server!

References:

&#8211; <a href="https://www.digitalocean.com/community/tutorials/how-to-create-a-ssl-certificate-on-nginx-for-centos-6" target="_blank">https://www.digitalocean.com/community/tutorials/how-to-create-a-ssl-certificate-on-nginx-for-centos-6</a>

&#8211; <a href="https://www.digitalocean.com/community/tutorials/how-to-install-an-ssl-certificate-from-a-commercial-certificate-authority" target="_blank">https://www.digitalocean.com/community/tutorials/how-to-install-an-ssl-certificate-from-a-commercial-certificate-authority</a>