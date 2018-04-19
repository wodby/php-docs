# Solr

You can configure Solr via environment variables that listed at https://github.com/wodby/solr

You can find URL to Solr admin UI from under Domains tab.

## Creating solr core

!!! tip "TIP"
    We automatically create a default solr core named `default` when no cores found.

Go to `Instance > Stack > Search Engine` page, copy and execute `Access container` on your host server to access the container with Solr. Copy `Create Solr core` command (edit to change core name), execute it inside of the container. Response `200` means that the core has been successfully created.

See [Solr stack](https://cloud.wodby.com/stackhub/dc8074a9-f27d-44a8-8f88-5922b4e16d2f) for more details.
