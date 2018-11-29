FROM php:7.2-fpm
ENV TZ 'Asia/Shanghai'
RUN docker-php-source extract \
    # 安装 gd 扩展
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
    # pcntl 扩展
    && cd /usr/src/php/ext/pcntl \
    && phpize \
    && ./configure --with-php-config=/usr/local/bin/php-config \
    && make \
    && make install \
    && touch /usr/local/etc/php/conf.d/php-ext-pcntl.ini \
    && echo extension=pcntl.so >> /usr/local/etc/php/conf.d/php-ext-pcntl.ini \
    # pdo_mysql 扩展
    && cd /usr/src/php/ext/pdo_mysql \
    && phpize \
    && ./configure --with-php-config=/usr/local/bin/php-config \
    && make \
    && make install \
    && touch /usr/local/etc/php/conf.d/php-ext-pdo_mysql.ini \
    && echo extension=pdo_mysql.so >> /usr/local/etc/php/conf.d/php-ext-pdo_mysql.ini \
    # zip 扩展
    && cd /usr/src/php/ext/zip \
    && phpize \
    && ./configure --with-php-config=/usr/local/bin/php-config \
    && make \
    && make install \
    && touch /usr/local/etc/php/conf.d/php-ext-zip.ini \
    && echo extension=zip.so >> /usr/local/etc/php/conf.d/php-ext-zip.ini \
    # 安装bcmanth扩展
    && cd /usr/src/php/ext/bcmath \
    && phpize \
    && ./configure --with-php-config=/usr/local/bin/php-config \
    && make \
    && make install \
    && touch /usr/local/etc/php/conf.d/php-ext-bcmath.ini \
    && echo extension=bcmath.so >> /usr/local/etc/php/conf.d/php-ext-bcmath.ini \
	# 安装intl 扩展
	&& apt-get update && apt-get install -y libicu-dev \
	&& cd /usr/src/php/ext/intl \
	&& phpize \
	&& ./configure --with-php-config=/usr/local/bin/php-config \
	&& make \
	&& make install \
	&& touch /usr/local/etc/php/conf.d/docker-php-ext-intl.ini \
	&& echo extension=intl.so >> /usr/local/etc/php/conf.d/docker-php-ext-intl.ini \
    && docker-php-source delete \
    && pecl install mongodb  \
    && pecl install redis

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php ./composer-setup.php \
    && php -r "unlink('composer-setup.php');" \
    && mv ./composer.phar /usr/local/bin/composer

RUN mkdir -p /mnt/CodingMonkey/log \
    && mkdir -p /mnt/CodingMonkey/run \
    && mkdir -p /mnt/CodingMonkey/cache \
    && mkdir -p /mnt/CodingMonkey/backup \
    && chmod a+rwx /mnt/CodingMonkey

RUN apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
