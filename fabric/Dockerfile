FROM python:2.7

RUN apt-get update && apt-get install -y rsync sed

RUN pip install 'fabric==1.14.0'

RUN apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

WORKDIR /opt/app/deploy

ENTRYPOINT ["fab"]