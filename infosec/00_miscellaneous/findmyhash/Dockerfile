FROM alpine:latest

RUN apk add --no-cache python py-pip wget \
    && wget --no-check-certificate https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/findmyhash/findmyhash_v1.1.2.py -O /root/findmyhash.py \
    && pip install --no-cache-dir httplib2 \
    && apk del --purge wget

ENTRYPOINT ["python", "/root/findmyhash.py"]
