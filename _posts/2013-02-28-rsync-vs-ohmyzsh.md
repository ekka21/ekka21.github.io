---
id: 281
title: rsync vs ohmyzsh
date: 2013-02-28T21:36:27+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=281
permalink: /2013/02/28/rsync-vs-ohmyzsh/
categories:
  - Linux
tags:
  - rsync
  - zsh
---
I have been using zsh for a month or two and loving every minute of it. I don&#8217;t know if I can live without it or not. However for some reason rsync and zsh, they just don&#8217;t play along with each other. When I tried to use rsync, I got this error message:

<pre>zsh: no matches found:</pre>

So what the hec is this!!!!!

After spend days and day of researching, I finally found the fix. Phew~~~

## 3.4: How do I turn off spelling correction/globbing for a single command?

In the first case, you presumably have `setopt correctall` in an initialisation file, so that zsh checks the spelling of each word in the command line. You probably do not want this behaviour for commands which do not operate on existing files.

The answer is to alias the offending command to itself with `nocorrect` stuck on the front, e.g.

<pre>alias rsync='nocorrect rsync'</pre>

To turn off globbing, the rationale is identical:

<pre>alias rsync='noglob rsync'</pre>

You can have both `nocorrect` and `noglob`, if you like, but the `nocorrect` must come first, since it is needed by the line editor, while `noglob` is only handled when the command is examined.

Note also that a shell function won&#8217;t work: the no&#8230; directives must be expanded before the rest of the command line is parsed.

_**The content above I found it on <a href="http://zsh.sourceforge.net/FAQ/zshfaq03.html" target="_blank">zsh.sourceforge.net</a> **section 3.4**_