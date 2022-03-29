FROM php:8.0-fpm

# composer install
COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer

# node.js install & yarn install
RUN curl https://deb.nodesource.com/setup_14.x | bash
RUN curl https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list

RUN apt-get update && apt-get install -y nodejs yarn postgresql-client

RUN apt update \
  && apt install -y g++ libicu-dev libpq-dev libzip-dev zip zlib1g-dev \
  && docker-php-ext-install intl opcache pdo pdo_pgsql pgsql
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www