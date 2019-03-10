FROM alpine:latest AS staging

RUN apk add --no-cache \
    -X http://dl-cdn.alpinelinux.org/alpine/edge/testing \
    -X http://dl-cdn.alpinelinux.org/alpine/edge/community \
        git \
        python2 \
        py2-pip \
        py2-pefile \
        py2-yaml \
        py2-netaddr \
        py2-ecdsa \
        py2-paramiko \
        py2-m2crypto \
        py2-cffi \
        py2-openssl \
        py2-requests \
        python2-dev \
        build-base \
        libressl-dev \
        linux-headers
RUN git clone https://github.com/n1nj4sec/pupy.git /pupy \
    && cd /pupy \
    && git submodule update --init \
    && rm -rf .git

WORKDIR /pupy
RUN pip2 install -r pupy/requirements.txt

WORKDIR /pupy/pupy
ADD https://github.com/n1nj4sec/pupy/releases/download/latest/payload_templates.txz /pupy/pupy
RUN tar xf payload_templates.txz \
    && rm payload_templates.txz

FROM alpine:latest

RUN apk add --no-cache python2 bash

COPY --from=staging /usr/lib/python2.7/site-packages /usr/lib/python2.7/site-packages
COPY --from=staging /pupy/pupy /pupy/pupy

WORKDIR /pupy/pupy
CMD ["python", "pupysh.py", "-h"]
