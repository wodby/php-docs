# PHP

You can configure PHP via environment variables that listed at [https://github.com/wodby/php](https://github.com/wodby/php#environment-variables)

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

### Remote debugging

Follow these steps to debug your application instance remotely with [xdebug](http://xdebug.org/docs/install):

1. Enable xdebug for your instance from `[Instance] > Stack > Settings`
2. Set up forwarding for xdebug: copy _Xdebug SSH tunnel_ command from `[Instance] > Stack > PHP` and run on your local machine
3. Make sure you have your IDE xdebug listener running on port 9000
4. Start debugging in IDE
5. Start your browser debug helper plugin ([Chrome](https://chrome.google.com/webstore/detail/xdebug-helper/eadndfjplgieldjbigjakmdgkmoaaaoc?hl=en) or [Firefox](https://addons.mozilla.org/en-us/firefox/addon/the-easiest-xdebug)) and open the page you want to debug

### Debugging with local environment

If you want to use Xdebug, uncomment this line to enable it in the compose file before starting containers:
```yml
PHP_XDEBUG: 1                 # Enable Xdebug extension
PHP_XDEBUG_DEFAULT_ENABLE: 1  # Comment out to disable (default).
```

If you would like to autostart xdebug, uncomment this line:
```yml
PHP_XDEBUG_REMOTE_AUTOSTART: 1     # Comment out to disable (default).
```

#### Xdebug on Mac OS X

There are two more things that need to be done on macOS in order to have Xdebug working (because there's no docker0 interface). Enable Xdebug as described in the previous section and uncomment the following two lines:

```yml
PHP_XDEBUG_REMOTE_CONNECT_BACK: 0         # Disabled for remote.host to work (enabled by default)
PHP_XDEBUG_REMOTE_HOST: "10.254.254.254"  # Setting the host (localhost by default)
```

You also need to have loopback alias with IP from above. You need this only once and that settings stays active until logout or restart.

```bash
sudo ifconfig lo0 alias 10.254.254.254
```
To add the loopback alias after a reboot, add the following contents to /Library/LaunchDaemons/docker4php.loopback.plist

```xml
<plist version="1.0">
  <dict>
    <key>Label</key>
    <string>Default Loopback alias</string>
    <key>ProgramArguments</key>
    <array>
      <string>/sbin/ifconfig</string>
      <string>lo0</string>
      <string>alias</string>
      <string>10.254.254.254</string>
      <string>netmask</string>
      <string>255.255.255.0</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
  </dict>
</plist>
```

#### Xdebug on Windows

You should do same things as for Mac OS. Enable Xdebug as described in the previous 2 sections and replace value of _PHP_XDEBUG_REMOTE_HOST_ to your DockerNAT ip assigned (by default it should be 10.0.75.1):

```yml
PHP_XDEBUG_REMOTE_HOST: "10.0.75.1"  # Setting the host (localhost by default)
```

You also need to check firewall not to block your connection. Disabling firewall should help.

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
