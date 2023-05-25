# iq_backend_theme

Backend theme for unicorn installations.\
Per default, gin's dark mode is enabled but each user can override the admin
theme settings the user profile (/user/edit).

Installation guide:

    // Install composer package
    composer require iqual/iq_backend_theme

    // Enable gin theme
    drush then gin

    // Enable dependency modules
    drush en gin_toolbar gin_login iq_backend_theme_helper

    // Enable theme
    drush then iq_backend_theme

    // Set as admin theme
    drush php:eval '$config = \Drupal::service("config.factory")->getEditable("system.theme"); $config->set("admin", "iq_backend_theme")->save();'

**Or as a sexy one-liner:**

    composer require iqual/iq_backend_theme && drush then gin && drush en gin_toolbar gin_login iq_backend_theme_helper && drush then iq_backend_theme && drush php:eval '$config = \Drupal::service("config.factory")->getEditable("system.theme"); $config->set("admin", "iq_backend_theme")->save();'

**Don't forget to uninstall Adminimal, once everything is working fine!**

    drush thun adminimal
    composer remove drupal/adminimal
