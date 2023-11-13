FROM php:8.2.11-apache

RUN apt update && apt install -y git
RUN git clone --depth 1 https://github.com/opencart/opencart.git /tmp/opencart
RUN mv /tmp/opencart/upload/* .

RUN apt install -y libzip-dev libpng-dev libcurl4-openssl-dev
RUN docker-php-ext-install curl gd zip mysqli

RUN mv config-dist.php config.php && mv admin/config-dist.php admin/config.php
RUN chmod 0777 config.php && chmod 0777 admin/config.php
RUN chown -R www-data:www-data system/storage

CMD ["apache2-foreground"]
