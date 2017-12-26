# Containers 

The PHP stack consist of the following containers:

| Container    | Versions           | Image                              |
| ------------ | ------------------ | ---------------------------------- |
| [Nginx]      | 1.13, 1.12         | [wodby/php-nginx]                  |
| [Apache]     | 2.4                | [wodby/php-apache]                 |
| [PHP]        | 7.1, 7.0, 5.6, 5.3 | [wodby/php]                        |
| [MariaDB]    | 10.2, 10.1         | [wodby/mariadb]                    |
| [PostgreSQL] | 10.1, 9.6          | [wodby/postgres]                   |
| [Redis]      | 4.0, 3.2           | [wodby/redis]                      |
| [Solr]       | 7.x, 6.x, 5.5, 5.4 | [wodby/solr]                       |
| [Webgrind]   | 1.5                | [wodby/webgrind]                   |
| [Blackfire]  | latest             | [blackfire/blackfire]              |
| [Rsyslog]    | latest             | [wodby/rsyslog]                    |
| [AthenaPDF]  | 2.10.0             | [arachnysdocker/athenapdf-service] |
| Mailhog      | latest             | [mailhog/mailhog]                  |
| Adminer      | 4.3                | [wodby/adminer]                    |
| phpMyAdmin   | latest             | [phpmyadmin/phpmyadmin]            |

!!! note "SSHD and Cron":
    For Wodby environments we additionally spin up copies of PHP services with overridden commands to run cron and ssh daemons. All environment variables added to PHP service will be automatically passed to [SSHD] and [Cron] services.

[Nginx]:  ../containers/nginx.md
[Apache]:  ../containers/apache.md
[AthenaPDF]:  ../containers/athenapdf.md
[PHP]:  ../containers/php.md
[SSHD]:  ../containers/ssh.md
[Cron]:  ../containers/cron.md
[MariaDB]:  ../containers/mariadb.md
[PostgreSQL]:  ../containers/postgres.md
[Redis]:  ../containers/redis.md
[Solr]:  ../containers/solr.md
[Memcached]:  ../containers/memcached.md
[OpenSMTPD]:  ../containers/opensmtpd.md
[Webgrind]:  ../containers/webgrind.md
[Blackfire]:  ../containers/blackfire.md
[Rsyslog]:  ../containers/rsyslog.md
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
