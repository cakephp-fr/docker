FROM cakephpfr/3.x:php56-fpm

RUN curl -sSL https://github.com/cakephp/docs_search/archive/master.tar.gz | tar -xzv
RUN cp -R docs_search-master/* /var/www/html/
RUN rm -rf docs_search-master

# Git
RUN apt-get update && apt-get install -y \
    git \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

# Composer
RUN curl -sS https://getcomposer.org/installer | php
RUN ./composer.phar install --prefer-dist

VOLUME /var/www/html
