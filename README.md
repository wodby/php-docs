# PHP stack documentation

Docs are built using [mkdocs](http://www.mkdocs.org)

Look at `build.sh` script to see how it works.

## To Publish New Version

* Update `build.sh`
* Update `index.html` to redirect to the latest version automatically.
* Create a new YAML file, like `5.5.1.yaml` if you are releasing version 5.5.1

## Running Locally

```bash
$ ./serve.sh
```

To run a specific version of the docs:

```bash
$ mkdocs serve --config-file 1.3.yaml
```
