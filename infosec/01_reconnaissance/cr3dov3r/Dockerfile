FROM alpine:latest

RUN apk add --no-cache git \
        g++ \
        libxml2 \
        libxml2-dev \
        libxslt-dev \
        python2 \
        python2-dev \
        py2-pip \
        py2-requests \
        py2-openssl \
    && git clone https://github.com/D4Vinci/Cr3dOv3r.git /Cr3dOv3r \
    && pip install --no-cache-dir -r /Cr3dOv3r/requirements.txt \
    && apk del --purge git g++ libxml2-dev libxslt-dev python2-dev py2-pip
WORKDIR /Cr3dOv3r
ENTRYPOINT ["python2", "Cr3d0v3r.py"]
CMD ["-h"]