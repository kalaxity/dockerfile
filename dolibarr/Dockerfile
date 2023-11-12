FROM php:8.1-apache

RUN apt update && apt install -y git
RUN git clone --depth 1 https://github.com/dolibarr/dolibarr
RUN touch ./dolibarr/htdocs/conf/conf.php && chmod a+w ./dolibarr/htdocs/conf/conf.php

RUN apt install -y libzip-dev libpng-dev libicu-dev libc-client-dev libkrb5-dev
RUN docker-php-ext-configure imap --with-kerberos --with-imap-ssl
RUN docker-php-ext-install calendar zip gd mysqli intl imap
#RUN a2enmod rewrite

CMD ["apache2-foreground"]
