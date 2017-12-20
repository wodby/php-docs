# MariaDB

See [MariaDB stack](https://cloud.wodby.com/stackhub/3aa42a7c-db8b-40e9-aa3c-06218724fae6)

## Redis

Install [redis module](https://www.drupal.org/project/redis) and enable redis integration under `[Instance] > Cache > Settings` page of Wodby dashboard to use it as an internal cache storage for Drupal. All required configuration already provided in [`wodby.settings.php` file](#settings-php).

See [Redis stack](https://cloud.wodby.com/stackhub/7548eb5a-c61b-4480-9f36-2501917692b3) for more details.

## OpenSMTPD

See [OpenSMTPD stack](https://cloud.wodby.com/stackhub/a545abfe-6882-4d47-b7b6-0e49516cefb7)

## Varnish

Read [this article](https://wunderkraut.se/blogg/purge-cachetags-varnish) to learn how to use Varnish with Drupal 8.

Varnish ignores the following GET parameters for cache id generation:

```
utm_source
utm_medium
utm_campaign
utm_content
gclid
cx
ie
cof
siteurl
```

See [Varnish stack](https://cloud.wodby.com/stackhub/0e6ce021-9c23-4478-a6e7-d37fd7c054eb) for more details.

## Solr

You can find URL to Solr admin UI from under Domains tab.

##### Creating solr core

> Since 4.4.0 we automatically create a default solr core named `default` when no cores found.

Go to `Instance > Stack > Search Engine` page, copy and execute `Access container` on your host server to access the container with Solr. Copy `Create Solr core` command (edit to change core name), execute it inside of the container. Response `200` means that the core has been successfully created.

##### Configure connection

Install [Search API Solr module](https://www.drupal.org/project/search_api_solr). Go to `Home » Administration » Configuration » Search and metadata » Search API`, create a new core or edit the default one. In expanded `CONFIGURE SOLR BACKEND` fieldset specify:

```
HTTP protocol: http
Solr host: solr
Solr port: 8983
Solr path: /solr
Solr core: [NAME OF YOUR CORE]
```

See [Solr for Drupal stack](https://cloud.wodby.com/stackhub/07a28bf6-6772-4ac2-9d3e-6b097e9038ff) for more details.

## Node.js

Server app for the [Node.js Integration Drupal module](https://www.drupal.org/project/nodejs). Usage:

1. Install [Node.js Integration Drupal module](https://www.drupal.org/project/nodejs) on your site
2. Visit the Node.js configuration page under the Configuration menu, and enter the connection information for your Node.js server application. Set host to `node` and service key can be found on `[Instance] > Stack > Node.js`

## Mailhog

If Mailhog service enabled and chosen as _Mail delivery service_ at `[Instance] > Stack > Settings` all outbound email will be caught by the Mailhog. You can view and release these emails from Mailhog UI, the URL can be found from Domains tab. When release specify `opensmtpd` in `SMTP server` field if you want to release emails to the built-in [opensmtpd](#opensmtpd) service.

## AthenaPDF

See [AthenaPDF stack](https://cloud.wodby.com/stackhub/249c859b-9368-41cc-b6a6-6148e6a77337)

## Blackfire

You can profile your Drupal application via blackfire.io by following the next steps:

* Enable blackfire probe extension by adding the environment variable `PHP_BLACKFIRE` with any value to PHP (Drupal) container
* Enable blackfire agent service in your stack
* Add environment variables `BLACKFIRE_SERVER_ID` and `BLACKFIRE_SERVER_TOKEN` to blackfire agent service with appropriate values from your blackfire.io profile
* Install blackfire companion extension for [Chrome](https://blackfire.io/docs/integrations/chrome) or [Firefox](https://blackfire.io/docs/integrations/firefox)
* Start profiling your app via the extension and see data from blackfire.io dashboard

Fore more details please refer to the official documentation: https://blackfire.io/docs/introduction

## Webgrind

Webgrind allows you view and analyze Xdebug profiler output and generate call graphs for visualisation. To use Webgrind first enable Xdebug profiler by [adding the following environment variables](https://docs.wodby.com/stacks/configuration.html) to your PHP container:

```
PHP_XDEBUG: 1
PHP_XDEBUG_PROFILER_ENABLE: 1
PHP_XDEBUG_PROFILER_ENABLE_TRIGGER: 1
PHP_XDEBUG_PROFILER_ENABLE_TRIGGER_VALUE: 1
```

Add `XDEBUG_PROFILE=1` param to GET or POST request (or set a cookie) you want to profile. Xdebug will generate profile files in `/mnt/files/xdebug/profiler`. Click Update in Webgrind to access the new information. See https://xdebug.org/docs/profiler to learn more about xdebug profiling.

> ! IMPORTANT: Xdebug profiling significantly decreases performance and increases resources usage. DO NOT USE it on Production servers.

## Rsyslog

Rsyslog can be used to stream your applications logs (watchdog). It's similar to using syslog, however there's no syslog in [PHP container](#php) (one process per container). Rsyslog will stream all incoming logs to a container output.

Here how you can use it with Monolog:

1. Install [monolog module](https://www.drupal.org/project/monolog). Make sure all dependencies being downloaded
2. Add new handler at `monolog/monolog.services.yml`:
```yml
monolog.handler.rsyslog:
  class: Monolog\Handler\SyslogUdpHandler
  arguments: ['rsyslog']
```
3. Rebuild cache (`drush cr`)
4. Use `rsyslog` handler for your channels
5. Find your logs in [rsyslog container output](https://docs.wodby.com/apps/logs.html)

Read [Logging in Drupal 8](https://www.wellnet.it/en/blog/logging-drupal-8) to learn more.
