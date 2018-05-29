FROM alpine:latest

RUN apk add --no-cache python2 \
        py2-pip \
        git \
        gcc \
        python2-dev \
        musl-dev \
        libffi-dev \
        libressl-dev \
    && pip install --no-cache-dir --upgrade git+https://github.com/allfro/pymiproxy.git \
    && apk del --purge \
        py2-pip \
        git \
        gcc \
        python2-dev \
        musl-dev \
        libffi-dev \
        libressl-dev

EXPOSE 8080
ENTRYPOINT ["python", "-m", "miproxy.proxy"]