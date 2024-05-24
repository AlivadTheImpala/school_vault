5/17
I set up a local environment using Local by GetFlyWheel
We walked through basic functions and how they work. Wordpress has a lot of its own built in functions that we can use and call arguments. Next up will be learning about arrays.
The Wordpress Username and password are: **alivadthedev**
**bd163114**

5/24:
We went over the importance of [[get_header ]]and [[get_footer]]
two very important [[Wordpress Functions]] 

We then created a new php file called header.php which includes youre average html head info. The `<body>` tag starts here, but ends in the footer.php file that was also created.

the header.php file contains the `<?php wp_head(); ?>` function inside the `<head>` tag, which allows WP to have control of injecting scripts or stylesheets, among other things.

to add an action to the `wp_head()` function, we created the functions.php file. In it we created a function called `uni_files()` which [[enqueue]]'s our stylesheet. 

function uni_files()
{
	wp_enqueue_style('uni_main_styles', get_stylesheet_uri());
}

To actually call that function we use `add_action('wp_enqueue_scripts', 'uni_files');`

Finally, to add the admin bar to our WordPress pages header, we also added `wp_footer();` This function is similar to wp_head in that it allows scripts or code into a page, but the main difference between this and is the wp_head loads things before content is rendered in order to allow for proper functionality of the page. wp_footer will load things like javascript and allow for better performance because it will load in after functionality and content have been rendered.





