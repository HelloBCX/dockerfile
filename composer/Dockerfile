FROM graze/composer

RUN apk add --no-cache \
    php7 \
    php7-intl \
    php7-pcntl \
    php7-tokenizer \
    php7-fileinfo \
    php7-simplexml \
    php7-dom \
    php7-gd \
    php7-xml \
    php7-xmlreader \
    php7-xmlwriter \
    php7-zip \
    php7-bcmath

RUN apk add --no-cache \
    php7-dev \
    php7-pear \
    curl

RUN apk add --no-cache \
    autoconf \
    gcc \
    g++ \
    libc-dev \
    make \
    git

# install swoole
RUN curl -o swoole-src-4.1.2.tar.gz https://codeload.github.com/swoole/swoole-src/tar.gz/v4.1.2 \
    && tar -zxvf swoole-src-4.1.2.tar.gz \
    && cd swoole-src-4.1.2 \
    && phpize \
    && ./configure --with-php-config=/usr/bin/php-config \
    && make -j$(nproc) && make install \
    && touch /etc/php7/conf.d/swoole.ini \
    && echo extension=swoole.so >> /etc/php7/conf.d/swoole.ini