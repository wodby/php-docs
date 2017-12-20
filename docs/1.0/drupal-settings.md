# Drupal settings

## settings.php

Wodby automatically adds include of `wodby.settings.php` to `settings.php` file inside of `sites/[SITE NAME]`. The value of `[SITE NAME]` is `default` unless you specify it distinctly on a new application deployment form. If directory doesn't exist Wodby will create it automatically.

Do not edit `wodby.settings.php`, all changes to this file will be reset.

The `wodby.settings.php` file contains configuration settings for integration with Wodby services such as Database, Cache storage and Reverse Caching Proxy. You can override settings specified in wodby.settings.php in your `sites/*/settings.php` file after the include of wodby.settings.php

## sites.php

Wodby automatically generates `sites.php` with the mapping of all domains attached via Wodby to the directory.

## Trusted hosts patterns

Wodby automatically adds trusted hosts patterns for all attached domains.

## Sync directory

Wodby automatically creates sync directory with a salt and specify it inside of `wodby.settings.php`.

## Files

Files for Drupal located in `/mnt/files` and symlinked to `sites/[SITE NAME]/files`.

## Base URL

The domain marked with primary flag will be used as a `$base_url` in settings.php file and as an `-l` parameter for cron.

## Multi-site

You can deploy your existing multi-site Drupal application as separate application instances. You will need to specify `Site directory` on the 2nd step of new application deployment form. For example if you have a directory `sites/my-drupal-site/*` you should specify `my-drupal-site`. This directory will be used to locate [`settings.php` file](#settings-php) and [files directory](#files). Also, [`sites.php` file](#sites-php) will be created automatically inside `sites/` with mapping of all domains attached to this instance.
