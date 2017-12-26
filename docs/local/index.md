# Local environment with Docker4PHP

Docker4PHP is an open-source project ([GitHub page](https://github.com/wodby/docker4php)) that provides pre-configured `docker-compose.yml` file from to spin up local environment on Linux, Mac OS X and Windows. 

## Requirements

* Install Docker ([Linux](https://docs.docker.com/engine/installation), [Docker for Mac](https://docs.docker.com/engine/installation/mac) or [Docker for Windows (10+ Pro)](https://docs.docker.com/engine/installation/windows))
* For Linux additionally install [docker compose](https://docs.docker.com/compose/install)

The PHP stack consist of the following containers:

[Nginx]: ../containers/nginx.md
[Apache]: ../containers/apache.md
[AthenaPDF]: ../containers/athenapdf.md
[PHP]: ../containers/php.md
[SSHD]: ../containers/ssh.md
[Cron]: ../containers/cron.md
[MariaDB]: ../containers/mariadb.md
[PostgreSQL]: ../containers/postgres.md
[Redis]: ../containers/redis.md
[Solr]: ../containers/solr.md
[Memcached]: ../containers/memcached.md
[OpenSMTPD]: ../containers/opensmtpd.md
[Webgrind]: ../containers/webgrind.md
[Blackfire]: ../containers/blackfire.md
[Rsyslog]: ../containers/rsyslog.md
[AthenaPDF]: ../containers/athenapdf.md

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
| Node         | latest             | `node`       | [_/node]                           |
| Portainer    | latest             | `portainer`  | [portainer/portainer]              | 
| Traefik      | latest             | `traefik`    | [_/traefik]                        | 
