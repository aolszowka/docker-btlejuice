FROM node:latest

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get -qq install bluetooth bluez libbluetooth-dev libudev-dev

RUN npm install -g btlejuice --unsafe-perm

EXPOSE 8000

ENTRYPOINT ["btlejuice-proxy"]
