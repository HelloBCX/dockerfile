FROM php:7.1-apache
RUN docker-php-source extract \
    && cd /usr/src/php/ext/gd \
    && php -r "copy('http://www.zlib.net/zlib-1.2.11.tar.gz','zlib-1.2.11.tar.gz');" \
    && tar -zxvf zlib-1.2.11.tar.gz \
    && cd zlib-1.2.11 \
    && ./configure && make && make install \
    && php -r "copy('https://jaist.dl.sourceforge.net/project/libpng/libpng16/1.6.34/libpng-1.6.34.tar.gz','libpng-1.6.34.tar.gz');" \
    && tar -zxvf libpng-1.6.34.tar.gz \
    && cd libpng-1.6.34 \
    && ./configure && make && make install \
    && cd /usr/src/php/ext/gd \
    && phpize \
    && ./configure --with-php-config=/usr/local/bin/php-config \
    && make \
    && make install \
    && touch /usr/local/etc/php/conf.d/php-ext-gd.ini \
    && echo extension=gd.so >> /usr/local/etc/php/conf.d/php-ext-gd.ini \
    && cd /usr/src/php/ext/pcntl \
    && phpize \
    && ./configure --with-php-config=/usr/local/bin/php-config \
    && make \
    && make install \
    && touch /usr/local/etc/php/conf.d/php-ext-pcntl.ini \
    && echo extension=pcntl.so >> /usr/local/etc/php/conf.d/php-ext-pcntl.ini \
    && cd /usr/src/php/ext/zip \
    && phpize \
    && ./configure --with-php-config=/usr/local/bin/php-config \
    && make \
    && make install \
    && touch /usr/local/etc/php/conf.d/php-ext-zip.ini \
    && echo extension=zip.so >> /usr/local/etc/php/conf.d/php-ext-zip.ini \
    && docker-php-source delete \
    && pecl install mongodb  \
    && pecl install redis \
