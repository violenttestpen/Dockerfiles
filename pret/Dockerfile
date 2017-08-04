FROM alpine:latest

WORKDIR /root
RUN apk add --no-cache \
        python \
        py-pip \
        python-dev \
        g++ \
        wget \
    && pip install --no-cache-dir colorama pysnmp \
    # Download the repository
    && wget --no-check-certificate https://github.com/RUB-NDS/PRET/archive/master.tar.gz \
    && tar -xzf master.tar.gz \
    # Cleanup
    && apk del --purge \
        py-pip \
        python-dev \
        g++ \
        wget \
    && rm -f master.tar.gz

ENTRYPOINT ["python", "/root/PRET-master/pret.py"]
