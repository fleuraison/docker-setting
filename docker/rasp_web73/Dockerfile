FROM php:7.3-fpm-alpine

COPY php.ini /usr/local/etc/php/conf.d/php.ini
# COPY www.conf /usr/local/etc/php-fpm.d/zzz-www.conf
RUN apk upgrade --no-cache update && \
  apk --no-cache upgrade && \
  apk --no-cache add icu-dev autoconf make g++ gcc \
     curl-dev \
     libmcrypt-dev \
     freetype-dev \
     libjpeg-turbo-dev \
     libpng-dev \
     libxml2-dev \
     zlib-dev \
     libzip-dev \
     libintl \
     git \
     vim \
     unzip \
     icu \
     imagemagick-dev \
     libssh2 \
     libssh2-dev \
     libxslt-dev \
     imap-dev \
    # libc-client-dev \
  && docker-php-ext-configure zip \ 
     --with-libzip \
  && docker-php-ext-configure gd \
     --with-freetype-dir=/usr/include/ \
     --with-jpeg-dir=/usr/include/ \
     --with-png-dir=/usr/include/ \
  && docker-php-ext-configure imap \
     --with-imap --with-imap-ssl \
  && apk add ca-certificates wget \
  && update-ca-certificates \
  && NPROC=$(grep -c ^processor /proc/cpuinfo 2>/dev/null || 1)\
  && docker-php-ext-install -j${NPROC} \
     mysqli \
     iconv \
     pdo \
     pdo_mysql \
     intl \ 
     curl \
     dom \
     mbstring \
     simplexml \
     zip \
     gd \
     imap \
    opcache \
#     /usr/src/php/ext/memcached \
   && pecl install xdebug-2.7.2 \
   && docker-php-ext-enable xdebug \

#  && rm -rf /usr/src/php/ext/memcached
  && php -r "readfile('http://getcomposer.org/installer');" > composer-setup.php \
  && php composer-setup.php --filename=composer \
  && php -r "unlink('composer-setup.php');" \
  && mv composer /usr/local/bin/composer
#

#  && apt-get install -y libmemcached-dev zlib1g-dev \
#  && pecl install memcached-3.0.3 \
#  && docker-php-ext-enable memcached opcache
