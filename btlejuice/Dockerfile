FROM node:latest

ENV BTLEJUICE_ProxyAddress 127.0.0.1

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get -qq install bluetooth bluez libbluetooth-dev libudev-dev

RUN npm install -g btlejuice --unsafe-perm

## Work around bluetooth-hci-socket missing
## https://github.com/DigitalSecurity/btlejuice/issues/15
RUN apt-get -qq install python && \
    npm install -g n && \
    n 8.9.0 && \
    npm install bluetooth-hci-socket --unsafe-perm

EXPOSE 8080

ENTRYPOINT btlejuice -u $BTLEJUICE_ProxyAddress -w
