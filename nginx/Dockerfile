FROM nginx

MAINTAINER cake17 <cake17@cake-websites.com>

COPY nginx.conf /etc/nginx/nginx.conf
COPY cakephp.conf /etc/nginx/sites-available/cakephp.conf

#RUN ln -s /etc/nginx/sites-available/cakephp.conf /etc/nginx/sites-enabled/app
#RUN rm /etc/nginx/sites-enabled/default

#RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

#RUN usermod -u 1000 www-data
