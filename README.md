# Laravel 5.5
Laravel 5.5 is built on docker

# PHP 7, Apache docker environment
Docker container with php 7.1 on Apache (httpd). Based on an docker-compose.yml file

# Requirements
- Docker and Docekr-compose
- GIT
- CURL

# Installation
1. clone this repository `git clone https://github.com/meysam-mahmoodi/dcoker-php7-apache.git`
2. navigate to it `cd dcoker-php7-apache`
3. Build docker image: `docker-compose build`
4. Run it: `docker run -d --name laravel55 -p 80:80`
5. Install Composer: 
```
docker exec laravel55 curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
docker exec laravel55 mv composer.phar /usr/local/bin/composer
```
6. Install dependecies: `cd /var/www/html/laravel && composer install `
6. open `http://localhost/laravel/public`