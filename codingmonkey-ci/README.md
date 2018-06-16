# bellcode/codingmonkey-dev

[![Docker Pulls](https://img.shields.io/docker/pulls/bellcode/codingmonkey-dev.svg)](https://hub.docker.com/r/bellcode/codingmonkey-dev/)

## tags

- 1.0


# 安装扩展

### 源码包扩展

例如安装gd
```
cd ~/php-7.1.10/ext/gd
&& phpize
&& ./configure --with-php-config=/usr/local/bin/php-config
&& make
&& make install
&& touch /usr/local/etc/php/conf.d/docker-php-ext-gd.ini
&& echo extension=gd.so >> /usr/local/etc/php/conf.d/docker-php-ext-gd.ini
```