# Laravel 5.5
Laravel 5.5 is built on docker

# PHP 7, Apache docker environment
Docker container with php 7.1 on Apache (httpd). Based on an docker-compose.yml file

# Requirements
- Docker and Docekr-compose
- GIT

# Installation
1. clone this repository `git clone https://github.com/meysam-mahmoodi/docker-php7-apache2.git`
2. navigate to it `cd docker-php7-apache2`
3. Build docker image: `docker-compose build`
4. Run it: `docker run -d --name laravel55 -p 80:80 docker-php7-apache2_php7`
5. Install Composer: 
```
docker exec -w /var/www/html laravel55 sh -c "curl --silent --show-error https://getcomposer.org/installer | php"
```
6. Install dependecies: 
```docker exec -w /var/www/html laravel55 php composer.phar install ```
7. open `http://localhost/public` or `http://your-server-ip-adress/public`
