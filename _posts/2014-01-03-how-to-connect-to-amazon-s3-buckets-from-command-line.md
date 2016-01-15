---
id: 373
title: How to connect to Amazon S3 buckets from command line?
date: 2014-01-03T22:00:32+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=373
permalink: /2014/01/03/how-to-connect-to-amazon-s3-buckets-from-command-line/
categories:
  - Linux
  - 'Tips &amp; Tricks'
tags:
  - amazon s3
  - s3
  - s3 bucket
---
Install s3cmd

<pre>brew install s3cmd
</pre>

Install gpg

<pre>brew install gpg
</pre>

Configure s3cmd

<pre>s3cmd --configure
</pre>

Just follow the prompted to add your Access Key, Secret Key and encryption password

gpg path is /usr/local/bin/gpg

Using the tool

Manual

<pre>man s3cmd
</pre>

<pre>s3cmd ls
</pre>

List content of a bucket

<pre>s3cmd ls s3://bucket_name
</pre>

Get files from a bucket to local

<pre>s3cmd get s3://bucket_name/file.png LOCAL_PATH
or s3cmd get -r s3://bucket_name LOCAL_PATH
</pre>

To Put files from local to a bucket

<pre>s3cmd -P put LOCAL_PATH/my-file.png  s3://bucket_name/
</pre>

To delete a file on a bucket

<pre>s3cmd del s3://bucket_name/my-file-to-delete.png
</pre>

Upload files recursively

<pre>s3cmd sync -r LOCAL_UPLOAD_DIR s3://BucketName/ --acl-public</pre>

Set a bucket to be public

<pre>s3cmd setacl s3://BucketName --acl-public --recursive</pre>

Check Disk usages on S3

<pre>s3cmd du s3://BucketName</pre>

Good article about using s3cmd:

  * <a href="http://s3tools.org/s3cmd-sync" target="_blank">http://s3tools.org/s3cmd-sync</a>
  * <a href="http://pervasivecode.blogspot.com/2010/11/setting-permissions-on-amazon-aws-s3.html" target="_blank">http://pervasivecode.blogspot.com/2010/11/setting-permissions-on-amazon-aws-s3.html</a>