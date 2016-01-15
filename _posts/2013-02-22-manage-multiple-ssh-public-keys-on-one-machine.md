---
id: 271
title: Manage multiple SSH Public Keys on one machine
date: 2013-02-22T01:28:09+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=271
permalink: /2013/02/22/manage-multiple-ssh-public-keys-on-one-machine/
categories:
  - Git
  - Linux
  - 'Tips &amp; Tricks'
tags:
  - multiple ssh keys
  - ssh-add
---
Sometime life is complicated. Today I have to have multiple ssh keys on my machine. There should be a way to have two or more keys on one machine right? Of cause!

After you do that, .ssh folder should look like this:

<pre>config
github
  - id_rsa
  - id_rsa.pub
user1
  - id_rsa
  - id_rsa.pub 
user2
  - id_rsa
  - id_rsa.pub 
known_hosts</pre>

Lastly, you will need to have a config file to tell your remote server knows which SSH Key to use.

<pre>Host github.com
	User git
	Hostname github.com
	IdentityFile ~/.ssh/github/id_rsa
Host pagodabox.com-user1
	User git
	Hostname git.pagodabox.com
	IdentityFile ~/.ssh/user1/id_rsa
Host pagodabox.com-user2
	User git
	Hostname git.pagodabox.com
	IdentityFile ~/.ssh/user2/id_rsa

#check ssh lists
ssh-add -l 

ssh-add ~/.ssh/github/id_rsa
ssh-add ~/.ssh/user1/id_rsa
ssh-add ~/.ssh/user2/id_rsa</pre>

Baam!