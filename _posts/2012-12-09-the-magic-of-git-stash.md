---
id: 204
title: The magic of git stash
date: 2012-12-09T00:28:00+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=204
permalink: /2012/12/09/the-magic-of-git-stash/
categories:
  - Git
tags:
  - git stash
  - stash
---
Show stash

<pre>git stash list</pre>

Saving stash

<pre>git stash 
or
git stash save 'comment'</pre>

Apply the lastest stash

<pre>Apply stash apply</pre>

Apply a specific stash

<pre>git stash apply stash@{4}</pre>

Apply a specific stash and remove it from the list

<pre>git stash pop stash@{4}</pre>

Remove stash

<pre>git stash drop stash@{0}</pre>

Apply a specific stash

<pre>git stash branch new_branch_name</pre>