FROM alpine:latest

WORKDIR /root
RUN echo "http://dl-cdn.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories \
    && apk add --no-cache binwalk

ENTRYPOINT ["/usr/bin/binwalk"]
