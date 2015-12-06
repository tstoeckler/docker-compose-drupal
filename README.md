## Requirements
- [Docker Compose](http://docs.docker.com/compose/)

## Installation
The `docker-compose.yml` assumes that a [Drupal](https://www.drupal.org/) installation using the [Composer template for Drupal projects](https://github.com/drupal-composer/drupal-project) is present in the `drupal` directory within the repository:
```bash
git clone https://github.com/drupal-composer/drupal-project.git drupal
```

## Usage
- Build the containers for later use:

        docker-compose build

- Start the MySQL server:

        docker-compose start mysql

- Start the Apache web server:

        docker-compose start apache

  The Drupal site is now available at [localhost:888/web](http://localhost:888/web) on the host

- Install [Composer](https://getcomposer.org/) dependencies:

        docker-compose run composer install

- Update Composer dependencies:

        docker-compose run composer update

- Install site with [Drush](https://github.com/drush-ops/drush/):

        docker-compose run php ../vendor/bin/drush site-install --db-url=mysql://root:root@mysql/drupal

- Rebuild caches with Drush:

        docker-compose run php ../vendor/bin/drush cache-rebuild
