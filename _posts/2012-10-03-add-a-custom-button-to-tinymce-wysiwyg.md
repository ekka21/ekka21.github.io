---
id: 36
title: Add a custom button to TinyMCE wysiwyg
date: 2012-10-03T15:53:39+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=36
permalink: /2012/10/03/add-a-custom-button-to-tinymce-wysiwyg/
categories:
  - Plugins Development
  - 'Tips &amp; Tricks'
  - Wordpress
tags:
  - shortcode
  - tinymce
  - wysiwyg
---
Today, I have to create a shortcode for my client to use but one thing I have to keep in mind is that they don&#8217;t know what the hec the shortcode is. So I &#8216;ve decided to dig further on how to make this easy for them to use.

I think creating a custom button that is embedded in WordPress TinyMCE is the way to go.

Here how I did it:

Add the code below to **functions.php**

<pre>function register_button( $buttons ) {
     array_push( $buttons, "|", "my_new_button" );
     return $buttons;
}

function add_plugin( $plugin_array ) {
   $plugin_array['my_new_button'] = get_stylesheet_directory_uri() . '/js/my_new_button.js';
   return $plugin_array;
}
function my_new_button() {
   if ( ! current_user_can('edit_posts') && ! current_user_can('edit_pages') )
   {
      return;
   }

   if ( get_user_option('rich_editing') == 'true' )
   {
      add_filter( 'mce_external_plugins', 'add_plugin' );
      add_filter( 'mce_buttons', 'register_button' );
   }

}
add_action('init', 'my_new_button');

//Short code
function my_shortcode_function( $atts, $content = null ) {
	extract(shortcode_atts(array(
			"some_value" =&gt; '',
	), $atts));
	$str = "&lt;a class="&quot;.$some_value.&quot;" href="#"&gt;".$content."&lt;/a&gt;";
	return $str;
}

add_shortcode("my_short_code", "my_shortcode_function");
</pre>

Create **path\_to\_your\_theme/js/my\_new_button.js**

<pre>(function() {
   tinymce.create('tinymce.plugins.my_new_button', {
      init : function(ed, url) {
         ed.addButton('my_new_button', {
            some_value  : 'SOME NAME HERE',
            image : url+'/link.png',
            onclick : function() {
               var co = prompt("Say Something here!");

               if (some_value != null)
               {
                 ed.execCommand('mceInsertContent', false, '[my_short_code]'+some_value+'[/my_short_code]');
               }
            }
         });
      },
      createControl : function(n, cm) {
         return null;
      }
   });
   tinymce.PluginManager.add('my_new_button', tinymce.plugins.my_new_button);
})();
</pre>

Happy clients Happy life&#8230;.peace! <img src="http://ekkachai.net/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />