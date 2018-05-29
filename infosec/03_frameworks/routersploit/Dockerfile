FROM alpine:latest

RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories \
    && apk add --no-cache bash python2 py2-requests py2-paramiko py2-beautifulsoup4 py2-snmp py2-setuptools git \
    && git clone https://github.com/reverse-shell/routersploit.git /routersploit \
    && apk del --purge git \
    && rm -rf /routersploit/.* \
    && ls /routersploit | grep -v routersploit | grep -v rsf.py | xargs rm -rf

ENTRYPOINT ["python", "/routersploit/rsf.py"]
