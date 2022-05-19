FROM php:5.5-apache

#RUN apt-get update && apt-get install -y \
#lsof

COPY apache2.conf /etc/apache2/conf-available/00-apache2.conf
RUN a2enconf 00-apache2.conf

#RUN pecl install xdebug-2.5.5
#RUN docker-php-ext-enable xdebug



RUN pecl install xdebug-2.4.1
RUN docker-php-ext-enable xdebug
#RUN echo "xdebug.remote_enable = on" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
#RUN echo "xdebug.remote_host = 192.168.31.223" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
#RUN echo "xdebug.remote_port = 9005" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini

RUN a2enmod expires headers filter deflate rewrite
RUN service apache2 restart

COPY php.ini /usr/local/etc/php/conf.d/00-custom.ini


