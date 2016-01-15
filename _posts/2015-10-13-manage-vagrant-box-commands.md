---
id: 591
title: Manage Vagrant Box commands
date: 2015-10-13T14:58:36+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=591
permalink: /2015/10/13/manage-vagrant-box-commands/
categories:
  - vagrant
tags:
  - vagrant
  - vagrant commands
---
<pre>vagrant init *IMAGE (*optional)
vagrant box add IMAGE
vagrant box list
vagrant box remove IMAGE *--box-version=0.0.0 (*optional)
vagrant destroy IMAGE or HASH
vagrant box update *--global (*optional: this flag will update all of your boxes)
vagrant package --output MyImage.box
</pre>