WP ADMIN TWITTER BOOTSTRAP
==========================

This a namespaced version of twitter bootstrap specifically for using in the wordpress admin menus.
The less files have been prefixed with. 

`.wp_bootstrap`

To use them in your wordpress plugin admin you need to copy the css js and images into your plugin directory. 

Register the css and js files in your plugin init file:

`wp_register_style( 'boostrap_css', plugins_url('css/bootstrap.css', __FILE__) );`    
`wp_register_style( 'bootstrap_responsive_css', plugins_url('css/bootstrap-responsive.css', __FILE__) );`
`wp_register_script( 'bootstrap_js', plugins_url('js/bootstrap.js', __FILE__) ); `

Add call them in your "settings" function:

`wp_enqueue_style('bootstrap_css');`
`wp_enqueue_style('boosttrap_responsive_css');`
`wp_enqueue_script('bootstrap_js');`

Then setup your settings wrapper div with the class.

`wp-bootstrap`

And you will have access to the bootstrap grid, responsiveness, and javascript plugins (modals, popovers, etc.)
See the bootstrap docs for details.


TWITTER BOOTSTRAP
=================

Bootstrap is Twitter's toolkit for kickstarting CSS for websites, apps, and more. It includes base CSS styles for typography, forms, buttons, tables, grids, navigation, alerts, and more.

To get started -- checkout http://twitter.github.com/bootstrap!


Developers
----------

We have included a makefile with convenience methods for working with the Bootstrap library.

+ **build** - `make`
Runs the LESS compiler to rebuild the `/less` files and compiles the docs pages. Requires lessc and uglify-js. <a href="http://twitter.github.com/bootstrap/less.html#compiling">Read more in our docs &raquo;</a>

+ **watch** - `make watch`
This is a convenience method for watching just Less files and automatically building them whenever you save. Requires the Watchr gem.


