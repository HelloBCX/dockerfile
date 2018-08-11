FROM nginx:1.14

RUN apt-get update && apt-get install -y wget make python gcc g++ \
    && wget https://nodejs.org/dist/v8.11.3/node-v8.11.3.tar.gz \
    && tar -zxvf node-v8.11.3.tar.gz \
    && cd node-v8.11.3 \
    && ./configure \
    && make \
    && make install

RUN npm i npm@latest -g \
	&& apt-get install -y autoconf  automake  libtool libffi-dev libpng-dev \
	&& wget http://ftp.cn.debian.org/debian/pool/main/libp/libpng/libpng12-0_1.2.49-1+deb7u2_amd64.deb \
    && apt-get install ./libpng12-0_1.2.49-1+deb7u2_amd64.deb

RUN apt-get remove -y python wget

RUN apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*