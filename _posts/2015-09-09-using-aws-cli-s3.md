---
id: 559
title: Using AWS CLI S3.
date: 2015-09-09T21:47:11+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=559
permalink: /2015/09/09/using-aws-cli-s3/
categories:
  - Linux
tags:
  - aws
  - awscli
  - s3
---
<pre>brew install awscli</pre>

<pre>aws configure</pre>

**Basic commands**

List all buckets

<pre>aws s3 ls</pre>

Make a new bucket

<pre>aws s3 s3://mybucket --region us-west-1</pre>

Delete a bucket 

<pre>aws s3 rb s3://mybucket --force</pre>

Copy a file from Local to s3

<pre>aws s3 cp ./test.txt s3://mybucket/test.txt</pre>

Copy a file from s3 to s3

<pre>aws s3 cp s3://mybucket/test.txt s3://mybucket/test2.txt</pre>

Copy a file from s3 to Local

<pre>aws s3 cp s3://mybucket/test.txt ./test.txt</pre>

Copy all files from s3 within a bucket to Local

<pre>aws s3 cp s3://mybucket . --recursive</pre>

Copy all files from Local to s3 bucket

<pre>aws s3 cp myDir s3://mybucket/ --recursive --exclude "*.gif" --acl public-read</pre>

Sync from a bucket to another bucket

<pre>aws s3 sync s3://mybucket s3://mybucket2 --acl public-read</pre>

I also alias aws s3 to just s3, so my command looks something like s3 ls, s3 cp, s3 mb, etc. 😉

Reference: <a href="http://docs.aws.amazon.com/cli/latest/reference/s3/index.html" target="_blank">Aws S3</a>