FROM hongjianghuang/cm_dev:1.7

RUN apt-get update && apt-get install -y libicu-dev

RUN cd /php-7.1.10/ext/intl \
&& phpize \
&& ./configure --with-php-config=/usr/local/bin/php-config \
&& make \
&& make install \
&& touch /usr/local/etc/php/conf.d/docker-php-ext-intl.ini \
&& echo extension=intl.so >> /usr/local/etc/php/conf.d/docker-php-ext-intl.ini

RUN pecl install swoole

RUN touch /usr/local/etc/php/conf.d/docker-php-ext-swoole.ini \
&& echo extension=swoole.so >> /usr/local/etc/php/conf.d/docker-php-ext-swoole.ini

RUN apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
