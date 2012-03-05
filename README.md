#Use Twitter Bootstrap in your WordPress plugins

This namespaced version of [Twitter Bootstrap](http://twitter.github.com/bootstrap/) specifically for using 
in the development of awesome User Interfaces for WordPress plugins. The toolkit gives you access to the 
entire Twitter Bootstrap package: base CSS, responsive scaffolding, buttons, tabs, forms, and javascript plugins.

To use the toolkit with your plugin:

Copy the `css`, `js`, and `images` folders into your plugin directory. 

Register the css and js files in your plugin `init` callback:

    wp_register_style( 'boostrap_css', plugins_url('css/bootstrap.css', __FILE__) );
    wp_register_style( 'bootstrap_responsive_css', plugins_url('css/bootstrap-responsive.css', __FILE__) );
    wp_register_script( 'bootstrap_js', plugins_url('js/bootstrap.js', __FILE__) );

Then, enqueue these files any time your UI depends on them:

    wp_enqueue_style('bootstrap_css');
    wp_enqueue_style('boosttrap_responsive_css');
    wp_enqueue_script('bootstrap_js');

Wrap the UI you want to style with Twitter Bootstrap in a namespaced container, e.g.,

    <div class="wp-bootstrap">
      <!-- Twitter Bootstrap styles are applied here -->
    </div>

#How did we do this?

With the power of [less](http://lesscss.org/). 

Twitter Bootstrap makes use of less in its stylesheets. We simply prefixed Twitter's styles with `.wp_bootstrap`.

Easy peasy. 

#Build bootstrap for WordPress

We have included a makefile with convenience methods for working with the Bootstrap library.

+ **build** - `make`
Runs the LESS compiler to rebuild the `/less` files and compiles the docs pages. Requires lessc and uglify-js. 
[Read more in Twitter's docs](http://twitter.github.com/bootstrap/less.html#compiling).

+ **watch** - `make watch`
This is a convenience method for watching just Less files and automatically building them whenever you save. 
Requires the Watchr gem.


