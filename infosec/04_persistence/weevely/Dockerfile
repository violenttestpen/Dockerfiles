FROM alpine:latest

WORKDIR /root
RUN apk add --no-cache \
        python \
        g++ \
        py-pip \
        yaml-dev \
        python-dev \
        wget \
    && pip install --no-cache-dir prettytable Mako PyYAML python-dateutil PySocks \
    && wget --no-check-certificate https://github.com/epinna/weevely3/archive/master.tar.gz -O - | tar xz \
    && apk del --purge g++ py-pip yaml-dev python-dev wget

RUN mv */ weevely3 \
    && ln -s /root/weevely3/weevely.py /usr/local/bin/weevely

ENTRYPOINT ["weevely"]