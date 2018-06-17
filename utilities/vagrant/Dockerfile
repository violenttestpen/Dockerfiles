FROM debian:stretch-slim

# docker run --privileged -v /dev/vboxdrv:/dev/vboxdrv -v /dev/vboxnetctl:/dev/vboxnetctl -it vagrant:latest

ENV VERSION 2.1.1

RUN apt-get update \
    && apt-get install -y wget \
    && wget https://releases.hashicorp.com/vagrant/${VERSION}/vagrant_${VERSION}_x86_64.deb -O /tmp/vagrant.deb \
    && dpkg -i /tmp/vagrant.deb \
    && apt-get purge -y wget \
    && rm -rf /var/cache/apt/*

ENTRYPOINT ["vagrant"]
