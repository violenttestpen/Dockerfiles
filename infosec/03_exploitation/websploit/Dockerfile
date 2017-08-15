FROM alpine:latest

WORKDIR /root
RUN apk add --no-cache python py-pip wget \
    && wget --no-check-certificate https://github.com/websploit/websploit/archive/master.tar.gz -O - | tar xz \
    && pip install --no-cache-dir scapy \
    && apk del --purge py-pip wget

ENTRYPOINT ["/root/websploit-master/websploit"]
