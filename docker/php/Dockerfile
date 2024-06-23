FROM php:8.3-fpm

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN apt-get update \
    && apt-get install -y git unzip libzip-dev libicu-dev libonig-dev \
    && docker-php-ext-install intl pdo_mysql mysqli zip bcmath

# nodejs install
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
    && apt-get install -y nodejs \
    && npm install npm@latest -g

COPY ./php.ini /usr/local/etc/php/php.ini

WORKDIR /var/www/html/src
