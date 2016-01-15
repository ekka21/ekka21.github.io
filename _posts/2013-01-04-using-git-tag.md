---
id: 233
title: Using git tag
date: 2013-01-04T20:52:03+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=233
permalink: /2013/01/04/using-git-tag/
categories:
  - Git
tags:
  - git tag
---
Showing a list of tags

<pre>git tag</pre>

Removing local tags

<pre>git tag -d TAG_NAME</pre>

Delete git tag remote

<pre>git push origin :refs/tags/12345</pre>

Showing Tag details

<pre>git show TAG_NAME</pre>

Tagging with a comment

<pre>git tag -a TAB_NAME -m 'my version 1.4'</pre>

Push a specific tag to remote

<pre>git push origin TAG_NAME</pre>

Push tags all at once

<pre>git push origin --tags</pre>

You can normally checkout the tag just like how you check out the branch

<pre>git checkout TAG_NAME</pre>

Remove all tags locally

<pre>git tag | xargs git tag -d</pre>