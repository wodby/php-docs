# Instance types

## Dev

Health checks disabled for all containers except database server

## Staging

The same as dev

## Production

* Health checks enabled for all containers
* The following environment variables added to PHP container:

| Environment Variable       | Value                             |
| -------------------------- | --------------------------------- |
| PHP_ERROR_REPORTING        | E_ALL & ~E_DEPRECATED & ~E_STRICT |
| PHP_DISPLAY_ERRORS         | Off                               |
| PHP_DISPLAY_STARTUP_ERRORS | Off                               |
| PHP_TRACK_ERRORS           | Off                               |
| PHP_ZEND_ASSERTIONS        | -1                                |
