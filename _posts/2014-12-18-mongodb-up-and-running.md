---
id: 468
title: MongoDB up and running
date: 2014-12-18T20:08:10+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=468
permalink: /2014/12/18/mongodb-up-and-running/
categories:
  - MongoDB
tags:
  - mongodb
  - nosql
---
Install through <a href="http://brew.sh/" target="_blank">Home Brew</a>

<pre>brew update && brew install mongodb
</pre>

Create a data folder

<pre>mkdir -p /usr/local/Cellar/mongodb/YOUR_VERIONS/bin/mongod/db 
</pre>

Setup an alias for starting up our MongoDB

<pre>alias mongoup='/usr/local/Cellar/mongodb/2.6.6/bin/mongod --dbpath db'
</pre>

Using it

<pre>$ mongo
&gt;show dbs
</pre>

Shell-centric cross-platform MongoDB management tool: http://robomongo.org/