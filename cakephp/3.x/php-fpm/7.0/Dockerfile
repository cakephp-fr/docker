FROM php:7.0-fpm

MAINTAINER cake17 <cake17@cake-websites.com>

# Install modules
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng12-dev \
        libpq-dev \
        g++ \
        libicu-dev \
    && docker-php-ext-configure intl \
    && docker-php-ext-install mbstring \
    && docker-php-ext-install intl \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install pdo_pgsql \
    && apt-get purge --auto-remove -y g++ \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN usermod -u 1000 www-data

CMD ["php-fpm"]
