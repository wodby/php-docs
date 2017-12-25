# PHP

You can configure PHP via environment variables that listed at https://github.com/wodby/php

## Composer

Composer package `hirak/prestissimo:^0.3` installed globally for www-data user to download dependencies in parallel.

## Environment variables

In addition to [global environment variables](https://docs.wodby.com/infrastructure/environment-variables.html), we provide the following variables in PHP container that you can use in your post-deployment scripts:

| Variable              | Description                                                      |
| --------------------- | ---------------------------------------------------------------- |
| `$APP_ROOT`           | `/var/www/html` by default                                       |
| `$HTTP_ROOT`          | e.g. `/var/www/html/web`                                         |
| `$WODBY_DIR_CONF`     | `/var/www/conf` by default                                       |
| `$WODBY_APP_NAME`     | My app                                                           |
| `$WODBY_HOST_PRIMARY` | example.com                                                      |
| `$WODBY_URL_PRIMARY`  | http://example.com                                               |
| `$WODBY_HOSTS`        | `[ "example.com", "dev.example.org", "dev.example.org.wod.by" ]` |

## Xdebug

Follow these steps to debug your application instance remotely with [xdebug](http://xdebug.org/docs/install):

1. Enable xdebug for your instance from `[Instance] > Stack > Settings`
2. Set up forwarding for xdebug: copy _Xdebug SSH tunnel_ command from `[Instance] > Stack > PHP` and run on your local machine
3. Make sure you have your IDE xdebug listener running on port 9000
4. Start debugging in IDE
5. Start your browser debug helper plugin ([Chrome](https://chrome.google.com/webstore/detail/xdebug-helper/eadndfjplgieldjbigjakmdgkmoaaaoc?hl=en) or [Firefox](https://addons.mozilla.org/en-us/firefox/addon/the-easiest-xdebug)) and open the page you want to debug

## Redirects

If you need to make a redirect from one domain to another you can do it by customizing configuration files of nginx or by adding the snippets below to your `settings.php` file.

Redirect from one domain to another:

```php
if (isset($_SERVER['WODBY_ENVIRONMENT_TYPE']) && $_SERVER['WODBY_ENVIRONMENT_TYPE'] == 'prod' && php_sapi_name() != "cli") {
    if ($_SERVER['HTTP_HOST'] == 'redirect-from-domain.com') {
      header('HTTP/1.0 301 Moved Permanently');
      header('Location: http://redirect-to-domain.com' . $_SERVER['REQUEST_URI']);
      exit();
    }
}
```

Redirect from multiple domains:

```php
if (isset($_SERVER['WODBY_ENVIRONMENT_TYPE']) && $_SERVER['WODBY_ENVIRONMENT_TYPE'] == 'prod' && php_sapi_name() != "cli") {
    $redirect_from = array(
      'redirect-from-domain-1.com',
      'redirect-from-domain-2.com',
    );

    if (in_array($_SERVER['HTTP_HOST'], $redirect_from)) {
      header('HTTP/1.0 301 Moved Permanently');
      header('Location: http://redirect-to-domain.com' . $_SERVER['REQUEST_URI']);
      exit();
    }
}
```

Redirect from HTTP to HTTPS can be enabled on a domain edit page from the dashboard.
