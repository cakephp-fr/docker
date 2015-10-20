FROM debian:jessie

MAINTAINER cake17 <cake17@cake-websites.com>

RUN apt-get update && apt-get install -y \
  php5-common \
  php5-cli \
  php5-fpm \
  php5-mysql \
  php5-apcu \
  php5-gd \
  php5-imagick \
  php5-curl \
  php5-intl

#COPY cakephp.ini /etc/php5/fpm/conf.d/cakephp.ini
#COPY cakephp.ini /etc/php5/cli/conf.d/cakephp.ini

COPY cakephp.pool.conf /etc/php5/fpm/pool.d/cakephp.pool.conf

RUN usermod -u 1000 www-data

CMD ["php5-fpm", "-F"]

EXPOSE 9000
