# Docker for CakePHP 3.x #

I took inspiration from the following repo:
- [eko/docker-symfony](https://github.com/eko/docker-symfony)
- [occitech/docker](https://github.com/occitech/docker)

## Install docker

First install docker on your computer with the [official doc](https://docs.docker.com/installation/#installation).

   On a mac, Docker Toolbox will install everything you need to be able to
   launch containers.

   IMPORTANT : On a mac, a small vm is installed, you can type
   `docker-machine ip default` (ex: 192.168.59.104) to know on which host
   containers will be launched. You will enter this address in your
   webbrowser to see your web pages.

## Add a docker-compose.yml file and replace config files

Clone the app skeleton on cakephp-fr github's repo and run composer:

    git clone git@github.com:cakephp-fr/app.git
    # the app skeleton is on the `docker` branch, so change for it
    git checkout --track origin/docker
    composer install

Then run:

    docker-compose up -d

You should see the welcome page in your webbrowser at the address http://MACHINE_IP:NGINX_PORT (ie. http://192.168.99.100:32779).

To get the Nginx Port, run `docker-compose ps` to know on which port the containers are running. You'll get something like:

  Name              Command          State               Ports              
----------------------------------------------------------------------------
app_app_1     /bin/bash               Up                                     
app_db_1      /entrypoint.sh mysqld   Up      0.0.0.0:32788->3306/tcp        
app_nginx_1   nginx -g daemon off;    Up      443/tcp, 0.0.0.0:32789->80/tcp
app_php_1     php-fpm                 Up      9000/tcp                     

So you can see that nginx is running on 32789's port in my case.

A reminder to get the MACHINE_IP, run `docker-machine ip default`. Returns in my case `192.168.99.100`


## Common dev tasks, usage of `composer` and `cake` console.

**For Composer**

The best way to me is to add a `composer.phar` at the root of your repository.

    # get CONTAINER_PHP_ID with docker ps
    docker exec -it CONTAINER_PHP_ID ./composer.phar install

**For database migrations**

To create your tables. You can use the [Migrations cakephp-plugin](https://github.com/cakephp/migrations):

    # get CONTAINER_PHP_ID with docker ps
    docker exec -it CONTAINER_PHP_ID ./bin/cake migrations migrate


## License ##

Copyright (c) [2014-2015] [cake17]

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
