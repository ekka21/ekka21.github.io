---
id: 92
title: Disable changing the theme
date: 2012-10-17T01:25:03+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=92
permalink: /2012/10/17/disable-changing-the-theme/
categories:
  - Theme
  - Wordpress
---
[code language=&#8221;php&#8221;]
  
/**
  
* Disable changing the theme for anyone a part from the admin user
  
*/
  
function disable\_changing\_theme\_for\_non_admin() {
	  
global $submenu, $userdata;
	  
get_currentuserinfo();
	  
if ($userdata->ID != 1) {
		  
unset($submenu\[&#8216;themes.php&#8217;\]\[5\]);
	  
}
  
}
  
add\_action(&#8216;admin\_init&#8217;, &#8216;disable\_changing\_theme\_for\_non_admin&#8217;);
  
[/code]

Code from <a href="http://www.paulund.co.uk/disable-changing-the-wordpress-theme" target="_blank">paulund.co.uk</a>