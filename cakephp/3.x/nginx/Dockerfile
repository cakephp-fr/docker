FROM nginx:1.9.5

MAINTAINER cake17 <cake17@cake-websites.com>

COPY nginx.conf /etc/nginx/nginx.conf
COPY conf.d/cakephp.conf /etc/nginx/conf.d/cakephp.conf

RUN rm /etc/nginx/conf.d/default.conf

RUN usermod -u 1000 www-data

CMD ["nginx", "-g", "daemon off;"]
