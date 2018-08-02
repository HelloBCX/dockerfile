FROM hongjianghuang/cm_dev:1.7

RUN apt-get update && apt-get install -y libicu-dev

RUN cd /usr/src && tar -xvf php.tar.xz

RUN cd /usr/src/php-7.1.10/ext/intl \
&& phpize \
&& ./configure --with-php-config=/usr/local/bin/php-config \
&& make \
&& make install \
&& touch /usr/local/etc/php/conf.d/docker-php-ext-icu.ini \
&& echo extension=icu.so >> /usr/local/etc/php/conf.d/docker-php-ext-icu.ini
