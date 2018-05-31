FROM alpine:latest

RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories \
    && apk add --no-cache git python2 py2-pip scapy py2-dnslib py2-crypto \
    && git clone https://github.com/sensepost/DET.git \
    && pip2 install --no-cache-dir -r /DET/requirements.txt \
    && apk del --purge py2-pip

WORKDIR /DET
ENTRYPOINT ["python2", "/DET/det.py", "-L"]
CMD ["-c", "config-sample.json"]
