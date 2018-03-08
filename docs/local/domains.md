# Domains Configuration

Docker4PHP uses [traefik](https://hub.docker.com/_/traefik) container for routing. By default, we use port `8000` to avoid potential conflicts but if port `80` is free on your host machine just replace traefik's ports definition in the compose file.

By default `BASE_URL` set to `${BASE_URL}`, you can change it in `.env` file.

Add `127.0.0.1 ${BASE_URL}` to your `/etc/hosts` file (some browsers like Chrome may work without it). Do the same for other default domains you might need from listed below:  

| Service      | Domain                            |
| ------------ | --------------------------------- |
| nginx/apache | http://${BASE_URL}:8000           |
| pma          | http://pma.${BASE_URL}:8000       |
| adminer      | http://adminer.${BASE_URL}:8000   |
| mailhog      | http://mailhog.${BASE_URL}:8000   |
| solr         | http://solr.${BASE_URL}:8000      |
| kibana       | http://kibana.${BASE_URL}:8000    |
| node         | http://front.${BASE_URL}:8000     |
| varnish      | http://varnish.${BASE_URL}:8000   |
| portainer    | http://portainer.${BASE_URL}:8000 |
| webgrind     | http://webgrind.${BASE_URL}:8000  |
