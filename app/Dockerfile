FROM php:7.4-apache

RUN apt update -y
RUN apt install -y git
RUN apt install -y nano
RUN apt install -y cron
RUN apt install -y libgmp-dev && docker-php-ext-install gmp
RUN docker-php-ext-install pdo pdo_mysql
RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli
RUN apt-get install -y \
        libzip-dev \
        zip \
  && docker-php-ext-install zip

# Enable Apache rewrite module
RUN a2enmod rewrite

# Add cron start command to the end of the Dockerfile
CMD ["cron", "-f"]