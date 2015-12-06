FROM php:cli

RUN \
  # Refresh package information
  apt-get update \
  && apt-get install --yes \
    # Install SQL command-line tools. This is needed for Drush.
    mysql-client postgresql-client sqlite \
    # Install development libraries needed for the PHP extensions.
    libpng12-dev libpq-dev libsqlite3-dev \
    --yes \
  # Install PHP extensions
  && docker-php-ext-install gd mbstring pdo_mysql pdo_pgsql pdo_sqlite
