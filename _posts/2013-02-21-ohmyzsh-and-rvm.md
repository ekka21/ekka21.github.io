---
id: 269
title: ohmyzsh and rvm
date: 2013-02-21T17:37:50+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=269
permalink: /2013/02/21/ohmyzsh-and-rvm/
categories:
  - Linux
  - ruby
tags:
  - rvm
---
I have rvm installed on my machine even before I start using <a href="https://github.com/robbyrussell/oh-my-zsh" target="_blank">ohmyzsh</a>. I &#8216;ve decided to make a switch because of its plugins and aliases. However, after I install zsh, my rvm is totally wracked. After days and days of trying to figure it out, I found the fix. All I had to do is to add this code below to ~/.zshrc

<pre>[[ -s "$HOME/.rvm/scripts/rvm" ]] &#038;&#038; . "$HOME/.rvm/scripts/rvm" 
</pre>

Woo hoo!