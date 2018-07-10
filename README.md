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
5. Install Composer inside it: 
```
docker exec -w /var/www/html laravel55 sh -c "curl --silent --show-error https://getcomposer.org/installer | php"
```
6. Install php packages: 
```docker exec -w /var/www/html laravel55 php composer.phar install ```
7. create a `.env` file: `docker exec -w /var/www/html cp .env.example .env`
8. generate a key: `docker exec -w /var/www/html php artisan key:generate` 
9. Open `http://localhost/public` or `http://your-server-ip-adress/public`

# Logging
Showing logs : `docker logs -f laravel55`

**Enabling php logs**
1. Attach the container: `docker exec -it laravel55 /bin/bash`
2. install nano: `apt-get install nano`
3. Create and open a php.ini: `nano /usr/local/etc/php/php.ini`
4. insert it content of file `etc/php/php.ini`
5. change `display_errors = Off` to `display_errors = On`
6. exit from container: `exit`
7. restart the container `docker restart laravel55`
