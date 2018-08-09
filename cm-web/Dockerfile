FROM nginx:1.14

RUN apt-get update && apt-get install -y nodejs

RUN apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*