# Quick start

!!! danger "Persistence of database data":
    You will lose MariaDB / PostgreSQL data if you run `docker-compose down`. Instead use `docker-compose stop` to stop containers. Alternatively, you can use a manual volume for mariadb data (see compose file), this way your data will always persist. 

1. Download `docker-compose.yml` file from the [latest stable release](https://github.com/wodby/docker4php/releases) to your PHP project root
2. Make sure`NGINX_SERVER_ROOT` (or `APACHE_SERVER_ROOT`) is set to your project public directory with `index.php` (by default `/var/www/html/public`)  
3. Optional: [import existing database](import-export.md) 
4. Optional: uncomment lines in the compose file to run _redis_, _elasticsearch_, _kibana_ etc
5. [Configure domains](domains.md) 
6. Run containers: `docker-compose up -d`
7. That's it! Your php application should be up and running at http://php.docker.localhost:8000
8. You can see status of your containers and their logs via portainer: http://portainer.php.docker.localhost:8000

You can stop containers by executing:
```bash
docker-compose stop
```

Have a problem? Submit a new issue on [GitHub](https://github.com/wodby/docker4php/issues) or ask [community on Slack](http://slack.wodby.com)

!!! tip "Permissions issues":
    To avoid potential problems with permissions between your host and containers please follow [these instructions](permissions.md)

!!! info "For macOS users":
    Out of box Docker for Mac volumes has poor performance. However there are workarounds, read more [here](docker-for-mac.md)

Feel free to adjust volumes and ports in the compose file for your convenience. 

