# Containers 

The PHP stack consist of the following containers:

[Nginx]:  /containers/nginx.md
[Apache]:  /containers/apache.md
[AthenaPDF]:  /containers/athenapdf.md
[PHP]:  /containers/php.md
[SSHD]:  /containers/ssh.md
[Cron]:  /containers/cron.md
[MariaDB]:  /containers/mariadb.md
[PostgreSQL]:  /containers/postgres.md
[Redis]:  /containers/redis.md
[Solr]:  /containers/solr.md
[Memcached]:  /containers/memcached.md
[OpenSMTPD]:  /containers/opensmtpd.md
[Webgrind]:  /containers/webgrind.md
[Blackfire]:  /containers/blackfire.md
[Rsyslog]:  /containers/rsyslog.md
[AthenaPDF]: https://cloud.wodby.com/stackhub/249c859b-9368-41cc-b6a6-6148e6a77337

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
