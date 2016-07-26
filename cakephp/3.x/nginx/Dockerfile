FROM nginx:1.11

MAINTAINER cake17 <cake17@cake-websites.com>

RUN rm /etc/nginx/conf.d/default.conf

COPY nginx.conf /etc/nginx/nginx.conf
COPY conf.d/cakephp.conf /etc/nginx/conf.d/cakephp.conf
