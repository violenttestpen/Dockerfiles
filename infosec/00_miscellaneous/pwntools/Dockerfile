FROM alpine:latest

RUN apk add --no-cache bash \
        python2 \
        py2-pip \
        python2-dev \
        git \
        gcc \
        make \
        musl-dev \
        libffi-dev \
        libressl-dev \
        linux-headers \
    && pip install --no-cache-dir --upgrade git+https://github.com/Gallopsled/pwntools.git \
    && apk del --purge py2-pip \
        python2-dev \
        git \
        gcc \
        make \
        musl-dev \
        libffi-dev \
        libressl-dev \
        linux-headers