---
id: 337
title: Posting a cross domain form using AJAX
date: 2013-07-05T16:19:34+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=337
permalink: /2013/07/05/posting-a-cross-domain-form-using-ajax/
categories:
  - jQuery
tags:
  - ajax
  - cross domains
---
I spent at least 2 hours and this happened a couple time already.

Remember, you CAN NOT post a form to a different domain using AJAX.

This is what your AJAX should look like.

<pre>$("#submit_btn").click(function() {
    var url = document.URL+'post.php';
    $.ajax({
           type: "POST",
           async: "true",
           url: url,
           data: $("#form68").serialize(),
           cache: "false",
    }).done(function(){
        alert('Woo Hooooo!');
    });

    return false;
  });</pre>

Your post.php should look like this

<pre>if ($_POST)
{
	$inputdata = array();
	foreach($_POST as $key => $val)
	{
	    $inputdata[] = $key."=".urlencode($val);
	}

	$query = implode("&", $inputdata);
	$initialization = curl_init("https://s1524474208.t.eloqua.com/e/f2");
	curl_setopt($initialization, CURLOPT_HEADER, 0);
	curl_setopt($initialization, CURLOPT_POST, 1);
	curl_setopt($initialization, CURLOPT_POSTFIELDS, $query);
	curl_setopt($initialization, CURLOPT_FOLLOWLOCATION, 0);
	curl_setopt($initialization, CURLOPT_REFERER, "http://local.rogator.com");
	curl_setopt($initialization, CURLOPT_RETURNTRANSFER, 1);
	$data = curl_exec($initialization);
	curl_close($initialization);	
}else{
  print 'what are your trying to do?';
}</pre>