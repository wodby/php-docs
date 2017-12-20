# Import

## From drush archive

This option is available on the 2nd step of a new application deployment form.

First, make sure you have [Drush installed](http://www.drush.org/en/master/install/), go to your Drupal root directory and execute a command:

```bash
$ drush archive-dump
```

or

```bash
$ drush ard
```

You should see output like:

```bash
$ drush ard
Archive saved to /Users/johndoe/drush-backups/archive-dump/20150604001227/drupalapp.20150604_001228.tar.gz
/Users/johndoe/drush-backups/archive-dump/20150604001227/drupalapp.20150604_001228.tar.gz
```

Now navigate to `Apps > Deploy` and choose drush archive on the 2nd step

## From separate archives

Import Drupal via separate archives for database and files. We support `.zip`, `.gz`, `.tar.gz`, `.tgz` and `.tar` archives. This option is available on the 2nd step of a new application deployment form and also on `[Instance] > Import` page of existing instance.

## Manual import import

In case your import data is huge it makes sense to import it manually from the server. Follow these steps:

1. Deploy your Drupal website from a git repository without importing data
2. Once the app is deployed, go to `Stack > SSH` and copy SSH command
3. Connect to the container by SSH
4. Copy your database archive here via `wget` or `scp`, make sure it's gzipped
5. Import unpacked database dump using `drush sql-cli < my-db-dump.sql`
6. Now let's import your files, cd to `/mnt/files`, use public and private subdirectories according to your needs
7. Copy your files archive here via `wget` or `scp` and unpack the archive
8. That's it! Clear Drupal cache and remove import artifacts

## Import between instances

You can import database and files from one instance to another regardless of whether instances are on the same server or not. Go to `[Instance] > Import` tab and select an instance where you'd like to import database/files from.
