FROM wordpress:php8.2-apache
RUN apt-get update && apt-get install -y --no-install-recommends nano libvips42 libzip-dev libffi-dev \
  && pecl install apcu-5.1.22 \
  && pecl install redis-5.3.7 \
  && pecl install igbinary-3.2.14 \
  && docker-php-ext-configure ffi --with-ffi \
  && docker-php-ext-install ffi \
  && docker-php-ext-configure shmop --enable-shmop \
  && docker-php-ext-install shmop \
  && docker-php-ext-enable apcu redis igbinary
ADD https://raw.githubusercontent.com/notglossy/docker-wordpress/main/php-ini.ini/standard-php.ini /usr/local/etc/php/php.ini
ADD https://raw.githubusercontent.com/roots/wp-password-bcrypt/master/wp-password-bcrypt.php /usr/src/wordpress/wp-content/mu-plugins/
