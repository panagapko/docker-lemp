FROM php:8-fpm

LABEL maintainer="Chris Panagapko <chris@panagapko.com>"

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Add user for laravel application
RUN groupadd -g 1000 www
RUN useradd -u 1000 -ms /bin/bash -g www www

# Change current user to www
USER www

CMD ["php-fpm"]

EXPOSE 9000