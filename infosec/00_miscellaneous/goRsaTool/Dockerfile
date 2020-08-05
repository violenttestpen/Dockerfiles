FROM ubuntu:focal AS staging

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update \
    && apt-get install -y git golang libflint-dev libecm-dev \
    && rm -rf /var/cache/apt/* \
    && go get github.com/sourcekris/goRsaTool

FROM ubuntu:focal

RUN apt-get update \
    && apt-get install -y libflint-2.5.2 libecm1 \
    && rm -rf /var/cache/apt/*

COPY --from=staging /root/go/bin/goRsaTool /goRsaTool
ENTRYPOINT ["/goRsaTool"]
CMD ["-help"]