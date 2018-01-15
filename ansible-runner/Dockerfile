FROM python:3.6

RUN apt-get update && apt-get install -y rsync
RUN pip install 'ansible==2.4.2'
RUN apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
