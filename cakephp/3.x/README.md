# Docker for CakePHP 3.x #

I took some tips from this [nice repo](https://github.com/eko/docker-symfony)

## Install docker

First install docker on your computer with the [official doc](https://docs.docker.com/installation/#installation).

   On a mac, Docker Toolbox will install everything you need to be able to
   launch containers.

   IMPORTANT : On a mac, a small vm is installed, you can type
   `docker-machine ip default` (ex: 192.168.59.104) to know on which host
   containers will be launched. You will enter this address in your
   webbrowser to see your web pages.

## Add a docker-compose.yml file and replace config files

- In your app, add a `docker-compose.yml` file at the root of your app

You can find an example in `cakephp/3.x/docker-composer.yml`.

- You can replace your `app.php` and `bootstrap.php` with the provided config
files.

Then run:

    docker-compose up -d


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
