---
id: 362
title: How to automatically deploy your app/site to the server using Git
date: 2013-12-24T17:01:48+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=362
permalink: /2013/12/24/how-to-automatic-deploy-your-appsite-to-the-server-using-git/
categories:
  - Git
tags:
  - auto deploy
  - git bare
---
**Login to your server**

<pre>mkdir /var/repo &#038;&#038; cd /var/repo
mkdir sample.com.git &#038; cd sample.com
git init --bare 
</pre>

&#8211;bare means that our folder will have no source files, just the version control.

<pre>cd /var/repo/sample.com.git
cat > post-receive
#!/bin/sh

git --work-tree=/var/www/domain.com --git-dir=/var/repo/site.git checkout -f
</pre>

When you finish typing, press &#8216;control-d&#8217; to save.

<pre>chmod +x post-receive
</pre>

**Local**

<pre>cd to_your_working_directory
mkdir sample.com &#038;&#038; cd sample.com
git init
git remote add prod ssh:/IP-ADDRESS/var/repo/sample.com.git
</pre>

Push to the server is as simple as 

<pre>git push prod master
</pre>

DONE!