FROM node:latest

ENV BTLEJUICE_ProxyAddress 127.0.0.1

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get -qq install bluetooth bluez libbluetooth-dev libudev-dev

RUN npm install -g btlejuice --unsafe-perm

EXPOSE 8080

ENTRYPOINT btlejuice -u $BTLJUICE_ProxyAddress -w
