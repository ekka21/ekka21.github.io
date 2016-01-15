---
id: 574
title: Vim workflow
date: 2015-10-23T16:56:22+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=574
permalink: /2015/10/23/vim-workflow/
categories:
  - 'Tips &amp; Tricks'
  - Vim
tags:
  - vim
---
Vim is Vi(Improve) editor. The learning curve is insane. Newly installed Vim is useless and you have to install and configure plugins. it is because its flexibility. My personal choice to vim is <a href="https://github.com/carlhuda/janus" target="_blank">https://github.com/carlhuda/janus</a>. It got almost everything I need out of the box.

Here are the vim command I learn over the weeks and I believe this list will keep growing.

Certain commands are prefixed with a key, which maps to \ by default. You can, for example, use let mapleader = &#8220;,&#8221; to change this to a comma. If you want this to be in effect for uses of in the .vimrc file, make sure to define this in ~/.vimrc.before

Install additional plugin

<pre>mkdir -p ~/.janus && cd ~/.janus && git clone URL</pre>

search and replace everything in an open file

<pre>:g/Text1/s//Text2/g</pre>

Turn on/off line number

<pre>:set nonumber or :set number</pre>

Show hidden files/folders in vim

<pre>shift+i</pre>

Show/Hide Nerdtree

<pre>ctl+b</pre>

Refresh Nerdtree

<pre>r</pre>

Create a new file in Vim/NerdTree, navigate to NerdTree

<pre>ma</pre>

Change root directory

<pre>C</pre>

To navigate to different window

<pre>ctl+w</pre>

Quick file search with live search

<pre>ctl+p</pre>

  * Press `<c-f>` and `<c-b>` to cycle between modes.
  * Press fn+f5 to purge the cache

Linux command line without leaving vim

<pre>:!Command line</pre>

List file buffer

<pre>:ls</pre>

Next buffer

<pre>:bn or :b#buffernumber</pre>

Next buffer

<pre>[b</pre>

previous buffer

<pre>]b</pre>

Resizing Vim split panel

<pre>ctl+v</pre>

Split a vertical panel

<pre>:vsp</pre>

Split a horizonal panel

<pre>:sp</pre>

Make current window panel full screen

<pre>:ZoomWin</pre>

Fix whiteSpace in vim

<pre>::FixWhitespace</pre>

In normal mode, type i and it will open a vertical split new panel

<pre>i</pre>

Automatically adding php namespacing(https://github.com/arnaud-lb/vim-php-namespace)
  
You have to install ctags

<pre>brew install ctags</pre>

Run the command below in laravel directory

<pre>ctags -R ./*</pre>

To use the autonamespace

<pre>,u</pre>

Commenting code using NerdCommenter

<pre>c #multiple line in Virtual mode
cc #one line
</pre>

Snippet can be found here
  
<a href="https://github.com/honza/vim-snippets/blob/master/snippets/php.snippets" target="_blank">https://github.com/honza/vim-snippets/blob/master/snippets/php.snippets</a>

https://github.com/godlygeek/tabular
  
Aligning text

<pre>:tab /=</pre>

Go to line

<pre>42G
42gg
:42&lt;CR></pre>