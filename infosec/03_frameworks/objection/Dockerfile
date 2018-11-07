FROM ubuntu:latest

ENV LC_ALL C.UTF-8
ENV LANG C.UTF-8

RUN apt-get update \
    && apt-get install --no-install-recommends -y python3 python3-pip \
    && pip3 install --no-cache-dir setuptools \
    && pip3 install --no-cache-dir objection \
    # Cleanup
    && apt-get autoclean \
    && rm -rf /var/cache/apt/*

ENTRYPOINT ["objection"]
CMD ["--help"]
