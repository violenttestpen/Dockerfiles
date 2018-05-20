FROM ubuntu:latest

ENV VERSION 70

RUN apt-get update \
    && apt-get install -y --no-install-recommends libgtk2.0 libx11-xcb1 wget \
    && wget --no-check-certificate -O /tmp/idafree_linux.run https://out7.hex-rays.com/files/idafree${VERSION}_linux.run \
    && chmod +x /tmp/idafree_linux.run \
    && echo -e "\n\n\n\n\ny\n/opt/idafree\n\n" | /tmp/idafree_linux.run \
    && apt-get purge -y wget \
    && rm -rf /tmp/idafree_linux.run /var/cache/apt/*

ENTRYPOINT ["/opt/idafree/ida64"]
