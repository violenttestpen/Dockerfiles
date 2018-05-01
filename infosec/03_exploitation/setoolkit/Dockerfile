FROM alpine:latest

RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories \
    && apk add --no-cache git python3 py3-pexpect py3-crypto py3-openssl py3-pefile \
    && git clone https://github.com/trustedsec/social-engineer-toolkit.git /social-engineer-toolkit \
    && python3 /social-engineer-toolkit/setup.py install \
    && ln -s /usr/bin/python3 /usr/bin/python

ENTRYPOINT ["/social-engineer-toolkit/setoolkit"]