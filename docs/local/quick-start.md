# Quick start

1. Download `docker4php.tar.gz` from the [latest stable release](https://github.com/wodby/docker4php/releases) and unpack to your PHP project root
2. Make sure `NGINX_SERVER_ROOT` (or `APACHE_SERVER_ROOT`) is set to your project public directory with `index.php` (by default `/var/www/html/public`)  
3. Ensure database credentials match in your database config and `.env` files
4. [Configure domains](domains.md) 
5. Optional: [import existing database](import-export.md) 
6. Optional: uncomment lines in the compose file to run [redis](../containers/redis.md), [elasticsearch](../containers/elasticsearch.md), [kibana](../containers/kibana.md), etc
7. Optional: macOS users please read [this](docker-for-mac.md)
8. Optional: Windows users please read [this](permissions.md#windows)
9. Run containers: `docker-compose up -d` or `make up` (see all [make commands](make-commands.md))
10. That's it! Your php application should be up and running at http://php.docker.localhost:8000
11. You can see status of your containers and their logs via portainer: http://portainer.php.docker.localhost:8000

!!! info "Optional files"
    If you don't need to [run multiple projects](multiple-projects.md) and don't use [docker-sync to improve volumes performance on macOS](docker-for-mac.md) feel free to delete `traefik.yml` and `docker-sync.yml` that come with the `docker4php.tar.gz`

You can stop containers by executing `docker-compose stop` or `make stop`

Have a problem? Submit a new issue on [GitHub](https://github.com/wodby/docker4php/issues) or ask [community on Slack](http://slack.wodby.com)

Feel free to adjust volumes and ports in the compose file for your convenience. 

