# Deployment 

## Vanilla Drupal

## Deployment with git

We recommend using [Composer](https://getcomposer.org) to manage dependencies in your repository:

1. Fork [our boilerplate](https://github.com/wodby/drupal-composer) or use the original [composer template for Drupal](https://github.com/drupal-composer/drupal-project)
2. Create `wodby.yml` in repository root (our boilerplate already has it) with the following content:
  ```yml
  pipeline:
    - name: Install dependencies
      type: command
      command: composer install --no-interaction --optimize-autoloader
      directory: $APP_ROOT
  ```
3. Enter `web` in `Codebase dir` input on the 2nd step of new application deployment form

## Deployment from CI tool

TBA