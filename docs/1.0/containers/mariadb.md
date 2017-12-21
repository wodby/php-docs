# MariaDB

You can configure MariaDB via environment variables that listed at [https://github.com/wodby/mariadb](https://github.com/wodby/mariadb)

## Local environment 

### Import existing database

if you want to import your database, uncomment the line for `mariadb-init` volume in your compose file. Create the volume directory `./mariadb-init` in the same directory as the compose file and put there your `.sql .sql.gz .sh` file(s). All SQL files will be automatically imported once MariaDB container has started.

### Export

Exporting all databases:
```bash
docker-compose exec mariadb sh -c 'exec mysqldump --all-databases -uroot -p"root-password"' > databases.sql
```

Exporting a specific database:
```bash
docker-compose exec mariadb sh -c 'exec mysqldump -uroot -p"root-password" my-db' > my-db.sql
```

For more details see [MariaDB stack](https://cloud.wodby.com/stackhub/3aa42a7c-db8b-40e9-aa3c-06218724fae6)
