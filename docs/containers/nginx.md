# Nginx

You can configure Nginx via environment variables that listed at https://github.com/wodby/php-nginx

If the default config and available environment variables are not enough for your customizations you can replace the config with your own:

1. Copy `/etc/nginx/conf.d/php.conf` to your codebase, adjust to your needs
2. Deploy code with your config file
3. Add new environment variable `NGINX_CONF_INCLUDE` for nginx service, the value should the path to your *.conf file (e.g. `/var/www/html/nginx.conf`)

## Mod pagespeed

Nginx comes with [mod_pagespeed](https://www.modpagespeed.com/) which is disabled by default. To enable it add `NGINX_PAGESPEED=on` environment variable to Nginx service.