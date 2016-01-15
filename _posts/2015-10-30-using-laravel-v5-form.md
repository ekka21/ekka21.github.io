---
id: 628
title: 'Using Laravel v5.* Form'
date: 2015-10-30T15:01:31+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=628
permalink: /2015/10/30/using-laravel-v5-form/
categories:
  - Laravel
tags:
  - form
  - laravel
  - laravel form
---
Add this line in composer.json and run composer update

<pre>"illuminate/html": "~5.0"</pre>

You can now use Laravel Form like this

<pre>{!! Form::open(array('url' =&gt; 'admin/cities')) !!}
  City name:
  {!! Form::text('title', old('title')) !!}
  {!! Form::submit('Save') !!}
{!! Form::close() !!}
</pre>

But if you decided not to use the magic sauce, you can compose your form field like this

<pre>&lt;form action="/admin/cities" method="POST"&gt;
 {{ csrf_field() }}
 &lt;input type="text" name="title" value="{{ old('title') }}"&gt;
 {{ method_field('DELETE') }}
 &lt;button type="submit"&gt;Delete&lt;/button&gt;
&lt;/form&gt;
</pre>