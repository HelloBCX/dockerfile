FROM golang:1.9.2

RUN apt-get update && apt-get install -y zip unzip
RUN go get github.com/BellPlanet/oss_uploader/cmd/oss-uploader
RUN apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
