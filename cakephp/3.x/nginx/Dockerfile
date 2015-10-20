FROM nginx:1.9.5

MAINTAINER cake17 <cake17@cake-websites.com>

ADD nginx.conf /etc/nginx/nginx.conf
ADD cakephp.conf /etc/nginx/sites-available/cakephp.conf

RUN ln -s /etc/nginx/sites-available/cakephp.conf /etc/nginx/sites-enabled/cakephp
RUN rm /etc/nginx/sites-enabled/default

RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

RUN usermod -u 1000 www-data
