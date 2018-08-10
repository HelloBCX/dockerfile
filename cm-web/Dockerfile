FROM nginx:1.14

RUN apt-get update && apt-get install -y wget make python gcc g++ \
    && wget https://nodejs.org/dist/v8.11.3/node-v8.11.3.tar.gz \
    && tar -zxvf node-v8.11.3.tar.gz \
    && cd node-v8.11.3 \
    && ./configure \
    && make \
    && make install

RUN apt-get remove -y make python gcc g++

RUN apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*