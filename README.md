Google Analytics for Dogma
==========================

Dogma is a simple framework for building localizable PHP-based web sites. See
[Dogma on Github](https://github.com/jkinner/dogma).

Google Analytics is a way to track the usage of your site. See 
[Google Analytics](http://www.google.com/analytics) for more information.

To use this module, set the following configuration properties:

    GoogleAnalyticsConfig::$account_id
    Dogma::$mode

To get an account, sign up at [Google Analytics](http://www.google.com/analytics). Google
Analytics tracking is *not enabled* when Dogma is in `DEV` mode (the default). When deploying
your application to production, make sure to set `Dogma::$mode` to `PROD`.

Using the module
----------------
To activate Google Analytics tracking for a particular page, render the `ga.php` template
into the template that renders the page, inside the `<head>` tag:

    <?php Dogma::render('ga.php') ?>

This line will render the necessary JavaScript to activate Google Analytics tracking. This
code will also activate a variable, `window._gaq`, that can be used inside your JavaScript.
Because tracking is only enabled in non-`DEV` mode, be sure to check whether the variable
is set:

    if (window._gaq) {
      // Do work!
    }

