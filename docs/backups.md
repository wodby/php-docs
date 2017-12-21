# Backups

This stack provides backup and restore actions for files (e.g. `sites/default/files`) and database. Learn more about backups from our [documentation](https://docs.wodby.com/apps/backups.html).

## Files backups

TBA

## Database backups

MariaDB run backups with [--single-transaction](https://dev.mysql.com/doc/refman/5.7/en/mysqldump.html) option to avoid tables locks.
