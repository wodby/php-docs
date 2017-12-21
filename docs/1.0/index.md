# Overview

## Overview

[Nginx]: containers/nginx.md
[Apache]: containers/apache.md
[AthenaPDF]: containers/athenapdf.md
[PHP]: containers/php.md
[SSHD]: containers/ssh.md
[Cron]: containers/cron.md
[MariaDB]: containers/mariadb.md
[PostgreSQL]: containers/postgres.md
[Redis]: containers/redis.md
[Solr]: containers/solr.md
[Memcached]: containers/memcached.md
[OpenSMTPD]: containers/opensmtpd.md
[Webgrind]: containers/webgrind.md
[Blackfire]: containers/blackfire.md
[Rsyslog]: containers/rsyslog.md
[AthenaPDF]: https://cloud.wodby.com/stackhub/249c859b-9368-41cc-b6a6-6148e6a77337

| Container | Description |
| --------- | ----------- |
| [Apache] | [Apache HTTP server](https://httpd.apache.org) is the most popular web server, developed and maintained by an open community of developers under the auspices of the Apache Software Foundation. |
| [Nginx] | Unlike traditional HTTP servers, [NGINX](http://nginx.org) does not rely on threads to handle requests. Instead it uses a much more scalable event-driven (asynchronous) architecture. This architecture uses small, but more importantly, predictable amounts of memory under load. |
| [PHP] | Currently supported versions: 7.x and 5.6. PHP container comes with a handful of most popular extensions. |
| [MariaDB] | [MariaDB](http://mariadb.org) is a [drop-in replacement](https://en.wikipedia.org/wiki/Drop-in_replacement) of MySQL and one of the most popular database servers in the world. It’s made by the original developers of MySQL and guaranteed to stay open source. |
| [PostgreSQL] | [PostgreSQL](http://postgres.org), often simply Postgres, is an object-relational database management system with an emphasis on extensibility and standards compliance.|
| [Redis] | [Redis](https://redis.io) is an open source, in-memory data structure store, used as a database, cache and message broker. Also known as memcached on steroids. The easiest way to improve performance is to connect an external in-memory cache storage. |
| [Memcached] | [Memcached](https://memcached.org) is a general-purpose distributed memory caching system. It is often used to speed up dynamic database-driven websites by caching data and objects in RAM to reduce the number of times an external data source must be read. |
| [OpenSMTPD] | [OpenSMTPD](https://www.opensmtpd.org) is free and simple mail transfer agent, implementation of the server-side SMTP protocol as defined by RFC 5321, with some additional standard extensions. |
| Varnish | [Varnish](http://varnish-cache.org) is a web application accelerator also known as a caching HTTP reverse proxy. You install it in front of any server that speaks HTTP and configure it to cache the contents. Varnish Cache is really, really fast. It typically speeds up delivery with a factor of 300 - 1000x, depending on your architecture. |
| [Solr] | [Solr](http://lucene.apache.org/solr) is a search engine built on Apache Lucene. Its major features include full-text search, hit highlighting, faceted search, real-time indexing, dynamic clustering, database integration. |
| Mailhog | [MailHog](https://github.com/mailhog/MailHog) is an email testing tool for developers. All outbound emails will be caught by Mailhog, you can view messages in the web UI and optionally release messages to real SMTP servers for delivery |
| [AthenaPDF] | [AthenaPDF](http://www.athenapdf.com) is a drop-in replacement for wkhtmltopdf using Electron and Go. |
| [Blackfire] | Agent for profiling via [blackfire.io](https://blackfire.io/docs/reference-guide/faq). |
| [Webgrind] | [Webgrind](https://github.com/jokkedk/webgrind) is a Xdebug profiling web frontend in PHP. |
| [Rsyslog] | [Rsyslog](http://www.rsyslog.com) is an enhanced multi-threaded syslogd used to stream applications logs. |
| PhpMyAdmin | [phpMyAdmin](https://www.phpmyadmin.net) is a free software tool written in PHP, intended to handle the administration of MySQL over the Web. |
| Adminer | [Adminer](https://www.adminer.org) is a simplified alternative to PhpMyAdmin. |

## Stack

The PHP stack consist of the following containers:

[wodby/php-nginx]: https://github.com/wodby/php-nginx
[wodby/php-apache]: https://github.com/wodby/php-apache
[wodby/php]: https://github.com/wodby/php
[wodby/mariadb]: https://github.com/wodby/mariadb
[wodby/postgres]: https://github.com/wodby/postgres
[wodby/redis]: https://github.com/wodby/redis
[wodby/varnish]: https://github.com/wodby/varnish
[wodby/solr]: https://github.com/wodby/solr
[wodby/memcached]: https://github.com/wodby/memcached
[wodby/webgrind]: https://hub.docker.com/r/wodby/webgrind
[blackfire/blackfire]: https://hub.docker.com/r/blackfire/blackfire
[wodby/rsyslog]: https://hub.docker.com/r/wodby/rsyslog
[arachnysdocker/athenapdf-service]: https://hub.docker.com/r/arachnysdocker/athenapdf-service
[mailhog/mailhog]: https://hub.docker.com/r/mailhog/mailhog
[wodby/adminer]: https://hub.docker.com/r/wodby/adminer
[phpmyadmin/phpmyadmin]: https://hub.docker.com/r/phpmyadmin/phpmyadmin
[portainer/portainer]: https://hub.docker.com/portainer/portainer
[_/node]: https://hub.docker.com/_/node
[_/traefik]: https://hub.docker.com/_/traefik

| Container    | Versions           | Service name | Image                              |
| ------------ | ------------------ | ------------ | ---------------------------------- |
| [Nginx]      | 1.13, 1.12         | `nginx`      | [wodby/php-nginx]                  |
| [Apache]     | 2.4                | `apache`     | [wodby/php-apache]                 |
| [PHP]        | 7.1, 7.0, 5.6, 5.3 | `php`        | [wodby/php]                        |
| [MariaDB]    | 10.2, 10.1         | `mariadb`    | [wodby/mariadb]                    |
| [PostgreSQL] | 10.1, 9.6          | `postgres`   | [wodby/postgres]                   |
| [Redis]      | 4.0, 3.2           | `redis`      | [wodby/redis]                      |
| Varnish      | 4.1                | `varnish`    | [wodby/varnish]                    |
| [Solr]       | 7.x, 6.x, 5.5, 5.4 | `solr`       | [wodby/solr]                       |
| [Memcached]  | 1.4                | `memcached`  | [wodby/memcached]                  |
| [Webgrind]   | 1.5                | `webgrind`   | [wodby/webgrind]                   |
| [Blackfire]  | latest             | `blackfire`  | [blackfire/blackfire]              |
| [Rsyslog]    | latest             | `rsyslog`    | [wodby/rsyslog]                    |
| [AthenaPDF]  | 2.10.0             | `athenapdf`  | [arachnysdocker/athenapdf-service] |
| Mailhog      | latest             | `mailhog`    | [mailhog/mailhog]                  |
| Adminer      | 4.3                | `adminer`    | [wodby/adminer]                    |
| phpMyAdmin   | latest             | `pma`        | [phpmyadmin/phpmyadmin]            |

!!! note "SSHD and Cron":
    For Wodby environments we additionally spin up copies of PHP services with overridden commands to run cron and ssh daemons. All environment variables added to PHP service will be automatically passed to [SSHD] and [Cron] services.

Additional containers for local environment:

| Container    | Versions           | Service name | Image                              |
| ------------ | ------------------ | ------------ | ---------------------------------- |
| Node         | latest             | `node`       | [_/node]                           |
| Portainer    | latest             | `portainer`  | [portainer/portainer]              |
| Traefik      | latest             | `traefik`    | [_/traefik]                        |
