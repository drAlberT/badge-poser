FROM circleci/php:7.4-fpm-node-browsers

USER root

# install system packages
RUN apt-get install -qqy libzip-dev libpng-dev libjpeg-dev libfreetype6-dev

# configure php packages
RUN docker-php-ext-configure gd --with-freetype=/usr/include/ --with-jpeg=/usr/include/

# install php requirements
RUN docker-php-ext-install zip iconv gd

USER circleci

# install prestissimo
RUN composer global require hirak/prestissimo
