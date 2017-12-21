# Importing and exporting data

## MariaDB

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

## Postgres

if you want to import your database, uncomment the line for `postgres-init` volume in your compose file. Create the volume directory `./postgres-init` in the same directory as the compose file and put there your `.sql .sql.gz .sh` file(s). All SQL files will be automatically imported once MariaDB container has started.
