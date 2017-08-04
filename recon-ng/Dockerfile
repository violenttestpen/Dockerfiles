FROM alpine:latest

# docker run -it --rm \
#     -v $HOME/.recon-ng:/root/.recon-ng \
#     --name recon-ng

WORKDIR /root
RUN apk add --no-cache \
        python \
        py-pip \
        build-base \
        python-dev \
        libxml2-dev \
        libxslt-dev \
        wget \
    && wget --no-check-certificate https://bitbucket.org/LaNMaSteR53/recon-ng/get/master.tar.gz \
    && tar xzf master.tar.gz \
    && mv */ recon-ng/ \
    && pip install -r recon-ng/REQUIREMENTS \
    && apk del --purge \
        py-pip \
        build-base \
        python-dev \
        libxml2-dev \
        libxslt-dev \
        wget \
    && rm -f master.tar.gz

ENTRYPOINT ["python", "/root/recon-ng/recon-ng"]
