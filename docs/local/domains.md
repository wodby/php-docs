# Domains Configuration

Docker4PHP uses [traefik](https://hub.docker.com/_/traefik) container for routing. By default, we use port `8000` to avoid potential conflicts but if port `80` is free on your host machine just replace traefik's ports definition in the compose file.

By default `BASE_URL` set to `php.docker.localhost`, you can change it in `.env` file.

Add `127.0.0.1 php.docker.localhost` to your `/etc/hosts` file (some browsers like Chrome may work without it). Do the same for other default domains you might need from listed below:  

| Service      | Domain                                     |
| ------------ | ------------------------------------------ |
| nginx/apache | http://php.docker.localhost:8000           |
| pma          | http://pma.php.docker.localhost:8000       |
| adminer      | http://adminer.php.docker.localhost:8000   |
| mailhog      | http://mailhog.php.docker.localhost:8000   |
| solr         | http://solr.php.docker.localhost:8000      |
| kibana       | http://kibana.php.docker.localhost:8000    |
| node         | http://front.php.docker.localhost:8000     |
| varnish      | http://varnish.php.docker.localhost:8000   |
| portainer    | http://portainer.php.docker.localhost:8000 |
| webgrind     | http://webgrind.php.docker.localhost:8000  |

