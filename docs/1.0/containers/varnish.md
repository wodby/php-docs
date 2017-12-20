# Varnish

Read [this article](https://wunderkraut.se/blogg/purge-cachetags-varnish) to learn how to use Varnish with Drupal 8.

Varnish ignores the following GET parameters for cache id generation:

```
utm_source
utm_medium
utm_campaign
utm_content
gclid
cx
ie
cof
siteurl
```

See [Varnish stack](https://cloud.wodby.com/stackhub/0e6ce021-9c23-4478-a6e7-d37fd7c054eb) for more details.
