[Test repo] Please use https://github.com/occitech/docker/tree/master/cakephp/3.x

1. **First install docker on your computer with the [official doc](https://docs.docker.com/installation/#installation).**

   On a mac, it will install boot2docker (a small vm) and you'll be able to
   launch Boot2docker app in the `Applications` folder that opens a Terminal
   bash.

   IMPORTANT : If you use boot2docker, get the ip of your boot2docker vm :
   `boot2docker ip` (ex: 192.168.59.104). You will enter this address in your
   webbrowser to see your web pages.

2. **Clone this repo anywhere in your computer.

   Go in the folder /nginx and launch `docker build -t cake17/nginx .`**
   Go in the folder /php-fpm and launch `docker build -t cake17/php-fpm .`**

   When it will be stable, I'll put this repo in the DockHub, so this 2. will
   not be necessary.

3. **In your app, add a `docker-compose.yml` file like in the `app/config/development/docker-compose.yml`:**

   And run `docker-compose up -d`



**Launch your migrations**

   To create your tables. You can use the [Migrations cakephp-plugin](https://github.com/cakephp/migrations).

        # get CONTAINER_APP_ID with docker ps
        docker exec -it CONTAINER_APP_ID ./bin/cake migrations migrate

**Launch composer update**




## License ##

Copyright (c) [2014-2015] [cake17]

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
