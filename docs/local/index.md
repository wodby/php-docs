# Local environment with Docker4PHP

Docker4PHP is an open-source project ([GitHub page](https://github.com/wodby/docker4php)) that provides pre-configured `docker-compose.yml` file from to spin up local environment on Linux, Mac OS X and Windows. 

## Requirements

* Install Docker ([Linux](https://docs.docker.com/engine/installation), [Docker for Mac](https://docs.docker.com/engine/installation/mac) or [Docker for Windows (10+ Pro)](https://docs.docker.com/engine/installation/windows))
* For Linux additionally install [docker compose](https://docs.docker.com/compose/install)

The `docker-compose.yml` file provides the following services:

| Container     | Versions           | Service name    | Image                              |
| ------------- | ------------------ | --------------- | ---------------------------------- |
| [Nginx]       | 1.15, 1.14, 1.13   | `nginx`         | [wodby/php-nginx]                  |
| [Apache]      | 2.4                | `apache`        | [wodby/php-apache]                 |
| [PHP]         | 7.x, 5.6           | `php`           | [wodby/php]                        |
| [MariaDB]     | 10.3, 10.2, 10.1   | `mariadb`       | [wodby/mariadb]                    |
| [PostgreSQL]  | 10, 9.x            | `postgres`      | [wodby/postgres]                   |
| [Redis]       | 4.0, 3.2           | `redis`         | [wodby/redis]                      |
| [Node.js]     | 9.11, 8.11, 6.14   | `node`          | [wodby/node]                       |
| [Varnish]     | 4.1                | `varnish`       | [wodby/varnish]                    |
| [Solr]        | 7.x, 6.x, 5.5, 5.4 | `solr`          | [wodby/solr]                       |
| Elasticsearch | 6.x, 5.6, 5.5, 5.4 | `elasticsearch` | [wodby/elasticsearch]              |
| Kibana        | 6.x, 5.6, 5.5, 5.4 | `kibana`        | [wodby/kibana]                     |
| [Memcached]   | 1.5                | `memcached`     | [wodby/memcached]                  |
| [Webgrind]    | 1.5                | `webgrind`      | [wodby/webgrind]                   |
| [Blackfire]   | latest             | `blackfire`     | [blackfire/blackfire]              |
| [Rsyslog]     | latest             | `rsyslog`       | [wodby/rsyslog]                    |
| [AthenaPDF]   | 2.10.0             | `athenapdf`     | [arachnysdocker/athenapdf-service] |
| [Mailhog]     | latest             | `mailhog`       | [mailhog/mailhog]                  |
| [OpenSMTPD]   | 6.0                | `opensmtpd`     | [wodby/opensmtpd]                  |
| Adminer       | 4.3                | `adminer`       | [wodby/adminer]                    |
| phpMyAdmin    | latest             | `pma`           | [phpmyadmin/phpmyadmin]            |
| Portainer     | latest             | `portainer`     | [portainer/portainer]              |
| Traefik       | latest             | `traefik`       | [_/traefik]                        |

[Apache]: ../containers/apache.md
[AthenaPDF]: ../containers/athenapdf.md
[Blackfire]: ../containers/blackfire.md
[Cron]: ../containers/cron.md
[Elasticsearch]: ../containers/elasticsearch.md
[Kibana]: ../containers/kibana.md
[MariaDB]: ../containers/mariadb.md
[Memcached]: ../containers/memcached.md
[Nginx]: ../containers/nginx.md
[Node.js]: ../containers/node.md
[OpenSMTPD]: ../containers/opensmtpd.md
[PHP]: ../containers/php.md
[PostgreSQL]: ../containers/postgres.md
[Redis]: ../containers/redis.md
[Rsyslog]: ../containers/rsyslog.md
[Solr]: ../containers/solr.md
[SSHD]: ../containers/ssh.md
[Webgrind]: ../containers/webgrind.md

[_/node]: https://hub.docker.com/_/node
[_/traefik]: https://hub.docker.com/_/traefik
[arachnysdocker/athenapdf-service]: https://hub.docker.com/r/arachnysdocker/athenapdf-service
[blackfire/blackfire]: https://hub.docker.com/r/blackfire/blackfire
[mailhog/mailhog]: https://hub.docker.com/r/mailhog/mailhog
[phpmyadmin/phpmyadmin]: https://hub.docker.com/r/phpmyadmin/phpmyadmin
[portainer/portainer]: https://hub.docker.com/portainer/portainer
[wodby/adminer]: https://hub.docker.com/r/wodby/adminer
[wodby/elasticsearch]: https://github.com/wodby/elasticsearch
[wodby/kibana]: https://github.com/wodby/kibana
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
