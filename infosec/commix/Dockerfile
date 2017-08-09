FROM alpine:latest

WORKDIR /root
RUN apk add --no-cache python wget \
    && wget --no-check-certificate https://github.com/commixproject/commix/archive/master.tar.gz -O - | tar xz \
    && apk del --purge wget

ENTRYPOINT ["/root/commix-master/commix.py"]
