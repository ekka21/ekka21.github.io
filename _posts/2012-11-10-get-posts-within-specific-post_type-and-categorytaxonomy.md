---
id: 148
title: Get posts within specific post_type and category/taxonomy
date: 2012-11-10T19:12:55+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=148
permalink: /2012/11/10/get-posts-within-specific-post_type-and-categorytaxonomy/
fb_social_plugin_settings_box_like:
  - default
fb_mentioned_pages:
  - 'a:0:{}'
fb_mentioned_pages_message:
  - 
fb_mentioned_friends:
  - 'a:0:{}'
fb_mentioned_friends_message:
  - 
fb_author_message:
  - 
fb_author_post_id:
  - 10151179041774565
fb_status_messages:
  - 'a:1:{i:0;a:2:{s:7:"message";s:104:"Posted to <a href="http://www.facebook.com/10151179041774565" target="_blank">your Facebook Timeline</a>";s:5:"error";s:0:"";}}'
categories:
  - Wordpress
tags:
  - custom post
  - taxonomy
---
Call the function by ek\_get\_post\_type($post\_type\_name, $post\_type\_taxonomy, $tax\_id, $number\_of\_posts);
  
Put this in your function.php
  
[code]
  
<?php
  
/**
   
* Get posts within specific post_type and category/taxonomy
   
* @param [type] $post_type [description]
   
* @param [type] $type_id [description]
   
* @param [type] $num [description]
   
* @return [type] String
   
*/
  
function ek\_get\_post\_type($post\_type\_name, $post\_type\_taxonomy, $tax\_id, $number\_of\_posts)
  
{
	  
$args=array(
        		  
&#8216;post\_type&#8217; => $post\_type,
        		  
&#8216;tax_query&#8217; => array(
															        
array(
															          
&#8216;taxonomy&#8217; => $type,
															          
&#8216;field&#8217; => &#8216;id&#8217;,
															          
&#8216;terms&#8217; => $cat_id,
															          
&#8216;operator&#8217; => &#8216;IN&#8217;
															        
)
															      
),
        		  
&#8216;posts\_per\_page&#8217; => $num,
        		  
&#8216;order&#8217; => &#8216;DESC&#8217;,
        		  
&#8216;orderby&#8217; => &#8216;date&#8217;
				  
);
  
?>
	  
<div id="#<?php print $cat_slug; ?>">
        
<div class="inner">
      	  
<?php
      		  
$loop = new WP_Query( $args );
					  
while ( $loop->have\_posts() ) : $loop->the\_post();
				  
?>
            
<div class="row">
              
<h3><?php the_title(); ?></h3>
              
<?php the_content(); ?>
            
</div>
          
<?php
					  
endwhile;
					  
wp\_reset\_postdata();
				  
?>
            
<div class="clearfix"></div>
        
</div>
      
</div>
  
<?php
  
}//end function
  
[/code]