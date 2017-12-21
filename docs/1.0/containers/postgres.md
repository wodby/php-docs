# PostgreSQL

You can configure PostgreSQL via environment variables that listed at [https://github.com/wodby/postgres](https://github.com/wodby/postgres)

## Local environment 

### Import existing database

if you want to import your database, uncomment the line for `postgres-init` volume in your compose file. Create the volume directory `./postgres-init` in the same directory as the compose file and put there your `.sql .sql.gz .sh` file(s). All SQL files will be automatically imported once MariaDB container has started.

For more details see [PostgreSQL stack](https://cloud.wodby.com/stackhub/3aa42a7c-db8b-40e9-aa3c-06218724fae6)
