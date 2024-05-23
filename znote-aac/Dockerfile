FROM php:apache
RUN a2enmod rewrite
RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli
RUN pecl install apcu && docker-php-ext-enable apcu && pecl clear-cache

RUN apt-get update; \
  apt-get install -y \
    build-essential \
    cmake \
    git-core; \
  apt-get clean && apt-get autoclean
RUN git clone https://github.com/Znote/ZnoteAAC.git /var/www/html

CMD ["apache2-foreground"]