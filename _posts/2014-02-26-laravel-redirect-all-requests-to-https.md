---
id: 391
title: Laravel redirect all requests to https
date: 2014-02-26T22:19:08+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=391
permalink: /2014/02/26/laravel-redirect-all-requests-to-https/
categories:
  - Laravel
tags:
  - https
  - laravel
  - secure
---
<pre>App::before(function($request)
{
    if( ! Request::secure())
    {
        return Redirect::secure(Request::getRequestUri());
    }
});
</pre>

Using Filters
  
Another option might be to create a filter like so. People generally store this also in app/filters.php.

<pre>Route::filter('force.ssl', function()
{
    if( ! Request::secure())
    {
        return Redirect::secure(Request::getRequestUri());
    }

});
</pre>

You can then enforce that new filter to any of your routes, route groups, or controllers like this.

Individual Route

<pre>Route::get('something', ['before' => 'force.ssl', function()
{
    return "This will be forced SSL";
}];
Route Group
</pre>

<pre>Route::group(['before' => 'force.ssl', function()
{
    // Routes here.
}
</pre>

Controller

You&#8217;ll need to do this in your controller&#8217;s __construct() method.

<pre>public function __construct()
{
    $this->beforeFilter('force.ssl');
}
</pre>

Source from <http://stackoverflow.com/questions/19967788/laravel-redirect-all-requests-to-https>