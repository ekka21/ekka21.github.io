---
id: 259
title: Install RVM with Ruby 1.9.3
date: 2013-02-09T06:18:47+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=259
permalink: /2013/02/09/install-rvm-with-ruby-1-9-3/
categories:
  - ruby
tags:
  - ruby
  - rvm
---
Install rvm

<pre>$ curl -L https://get.rvm.io | bash -s stable --ruby</pre>

Install ruby VERSION X.X.X

<pre>$ brew update
$ brew tap homebrew/dupes
$ brew install autoconf automake apple-gcc42
$ rvm pkg install openssl
$ rvm install 1.9.3 (or `rvm reinstall all --force` in case you had already installed ruby)
$ sudo ln -s /usr/local/bin/gcc-4.2 /usr/bin/gcc-4.2</pre>