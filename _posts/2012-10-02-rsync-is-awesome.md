---
id: 23
title: Rsync is awesome!
date: 2012-10-02T15:57:41+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=23
permalink: /2012/10/02/rsync-is-awesome/
categories:
  - Linux
tags:
  - rsync
---
Here is how I transfer file outside or my git repo from one machine another

**Remote -> Local**

[code]
  
rsync -avz USER@REMOTE\_IP\_ADDRESS:ABS\_PATH\_TO\_MY\_UPLOADS/* LOCAL\_DESTINATION\_PATH
  
[/code]

**Local -> Remote**

[code]
  
rsync -avz LOCAL\_DESTINATION\_PATH ssh USER@REMOTE\_IP\_ADDRESS:ABS\_PATH\_TO\_MY\_REMOTE_UPLOADS
  
[/code]