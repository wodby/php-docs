# Overview

| Container | Description |
| --------- | ----------- |
| [Nginx](containers/nginx.md) | Unlike traditional HTTP servers, [NGINX](http://nginx.org) does not rely on threads to handle requests. Instead it uses a much more scalable event-driven (asynchronous) architecture. This architecture uses small, but more importantly, predictable amounts of memory under load. |
| [Apache](containers/apache.md) | [Apache HTTP server](https://httpd.apache.org) is the most popular web server, developed and maintained by an open community of developers under the auspices of the Apache Software Foundation. |
| [PHP](containers/php.md) | Currently two mainlines of [PHP 7](http://php.net) are supported: 7.0 and 7.1. PHP container comes with a handful of most popular extensions and also includes [Drush](http://drush.org) and [Drupal Console](https://drupalconsole.com). |
| [MariaDB](containers/mariadb.md) | [MariaDB](http://mariadb.org) is a [drop-in replacement](https://en.wikipedia.org/wiki/Drop-in_replacement) of MySQL and one of the most popular database servers in the world. It’s made by the original developers of MySQL and guaranteed to stay open source. |
| [Redis](containers/redis.md) | [Redis](https://redis.io) is an open source, in-memory data structure store, used as a database, cache and message broker. Also known as memcached on steroids. The easiest way to improve performance of Drupal is to connect an external in-memory cache storage. |
| [OpenSMTPD](https://cloud.wodby.com/stackhub/a545abfe-6882-4d47-b7b6-0e49516cefb7) | [OpenSMTPD](https://www.opensmtpd.org) is free and simple mail transfer agent, implementation of the server-side SMTP protocol as defined by RFC 5321, with some additional standard extensions. |
| [Varnish](containers/varnish.md) | [Varnish](http://varnish-cache.org) is a web application accelerator also known as a caching HTTP reverse proxy. You install it in front of any server that speaks HTTP and configure it to cache the contents. Varnish Cache is really, really fast. It typically speeds up delivery with a factor of 300 - 1000x, depending on your architecture. |
| [Solr](containers/solr.md) | [Solr](http://lucene.apache.org/solr) is a search engine built on Apache Lucene. Its major features include full-text search, hit highlighting, faceted search, real-time indexing, dynamic clustering, database integration. |
| [Node.js](containers/nodejs.md) | Server app for the Node.js Integration Drupal module. https://www.drupal.org/project/nodejs. |
| Mailhog | [MailHog](https://github.com/mailhog/MailHog) is an email testing tool for developers. All outbound emails will be caught by Mailhog, you can view messages in the web UI and optionally release messages to real SMTP servers for delivery |
| [AthenaPDF](https://cloud.wodby.com/stackhub/249c859b-9368-41cc-b6a6-6148e6a77337) | [AthenaPDF](http://www.athenapdf.com) is a drop-in replacement for wkhtmltopdf using Electron and Go. |
| [Blackfire](containers/blackfire.md) | Agent for profiling via [blackfire.io](https://blackfire.io/docs/reference-guide/faq). |
| [Webgrind](containers/webgrind.md) | [Webgrind](https://github.com/jokkedk/webgrind) is a Xdebug profiling web frontend in PHP. |
| [Rsyslog](containers/rsyslog.md) | [Rsyslog](http://www.rsyslog.com) is an enhanced multi-threaded syslogd used to stream applications logs. |
| PhpMyAdmin | [phpMyAdmin](https://www.phpmyadmin.net) is a free software tool written in PHP, intended to handle the administration of MySQL over the Web. |
| Adminer | [Adminer](https://www.adminer.org) is a simplified alternative to PhpMyAdmin. |
