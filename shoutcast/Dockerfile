FROM ubuntu:16.04
LABEL maintainer "Charles Butler <chuck@linuxlab.sh>"

ENV ADMINPASS=admin
ENV STREAMPASS=stream
ENV PORTBASE=8000

RUN mkdir /opt/shoutcast && \
    mkdir /var/log/shoutcast

WORKDIR /opt/shoutcast

RUN apt-get update && \ 
    apt-get install -y wget && \
    wget http://download.nullsoft.com/shoutcast/tools/sc_serv2_linux_x64-latest.tar.gz && \
    tar -xzf sc_serv2_linux_x64-latest.tar.gz && \
    apt-get remove -y wget && \
    rm -rf /var/lib/apt/lists/*

ADD start.sh /start.sh

EXPOSE $PORTBASE

ENTRYPOINT ["/start.sh"]

