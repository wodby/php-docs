# Containers 

The PHP stack consist of the following containers:

| Container    | Versions           | Image                              |
| ------------ | ------------------ | ---------------------------------- |
| [Apache]     | 2.4                | [wodby/php-apache]                 |
| [AthenaPDF]  | 2.10.0             | [arachnysdocker/athenapdf-service] |
| [Blackfire]  | latest             | [blackfire/blackfire]              |
| [Crond]      | -//-               | [wodby/php]                        |
| [Mailhog]    | latest             | [mailhog/mailhog]                  |
| [MariaDB]    | 10.3, 10.2, 10.1   | [wodby/mariadb]                    |
| [Memcached]  | 1.5                | [wodby/memcached]                  |
| [Nginx]      | 1.15, 1.14, 1.13   | [wodby/php-nginx]                  |
| [Node.js]    | 9.11, 8.11, 6.14   | [wodby/node]                       |
| [OpenSMTPD]  | 6.0                | [wodby/opensmtpd]                  |
| [PHP]        | 7.x, 5.6, 5.3      | [wodby/php]                        |
| [PostgreSQL] | 10, 9.x            | [wodby/postgres]                   |
| [Redis]      | 4.0, 3.2           | [wodby/redis]                      |
| [Rsyslog]    | latest             | [wodby/rsyslog]                    |
| [Solr]       | 7.x, 6.x, 5.5, 5.4 | [wodby/solr]                       |
| [SSHD]       | -//-               | [wodby/php]                        |
| [Varnish]    | 4.1                | [wodby/varnish]                    |
| [Webgrind]   | 1.5                | [wodby/webgrind]                   |
| Adminer      | 4.3                | [wodby/adminer]                    |
| phpMyAdmin   | latest             | [phpmyadmin/phpmyadmin]            |

!!! note "SSHD and Cron"
    For Wodby environments we additionally spin up copies of PHP services with overridden commands to run cron and ssh daemons. All environment variables added to PHP service will be automatically passed to [SSHD] and [Cron] services.

[Apache]:  ../containers/apache.md
[AthenaPDF]:  ../containers/athenapdf.md
[Blackfire]:  ../containers/blackfire.md
[Cron]:  ../containers/cron.md
[Mailhog]:  ../containers/mailhog.md
[MariaDB]:  ../containers/mariadb.md
[Memcached]:  ../containers/memcached.md
[Nginx]:  ../containers/nginx.md
[Node.js]:  ../containers/node.md
[OpenSMTPD]:  ../containers/opensmtpd.md
[PHP]:  ../containers/php.md
[PostgreSQL]:  ../containers/postgres.md
[Redis]:  ../containers/redis.md
[Rsyslog]:  ../containers/rsyslog.md
[Solr]:  ../containers/solr.md
[SSHD]:  ../containers/ssh.md
[Varnish]:  ../containers/varnish.md
[Webgrind]:  ../containers/webgrind.md

[arachnysdocker/athenapdf-service]: https://hub.docker.com/r/arachnysdocker/athenapdf-service
[blackfire/blackfire]: https://hub.docker.com/r/blackfire/blackfire
[mailhog/mailhog]: https://hub.docker.com/r/mailhog/mailhog
[phpmyadmin/phpmyadmin]: https://hub.docker.com/r/phpmyadmin/phpmyadmin
[wodby/adminer]: https://hub.docker.com/r/wodby/adminer
[wodby/mariadb]: https://github.com/wodby/mariadb
[wodby/memcached]: https://github.com/wodby/memcached
[wodby/node]: https://github.com/wodby/node
[wodby/opensmtpd]: https://github.com/wodby/opensmtpd
[wodby/php-apache]: https://github.com/wodby/php-apache
[wodby/php-nginx]: https://github.com/wodby/php-nginx
[wodby/php]: https://github.com/wodby/php
[wodby/postgres]: https://github.com/wodby/postgres
[wodby/redis]: https://github.com/wodby/redis
[wodby/rsyslog]: https://hub.docker.com/r/wodby/rsyslog
[wodby/solr]: https://github.com/wodby/solr
[wodby/varnish]: https://github.com/wodby/varnish
[wodby/webgrind]: https://hub.docker.com/r/wodby/webgrind
