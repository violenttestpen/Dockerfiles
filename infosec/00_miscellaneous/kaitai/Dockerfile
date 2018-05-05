FROM ubuntu:latest

ENV VERSION 0.8

RUN apt-get update \
    && apt-get install --no-install-recommends -y wget unzip openjdk-8-jre-headless \
    && wget https://dl.bintray.com/kaitai-io/universal/${VERSION}/kaitai-struct-compiler-${VERSION}.zip \
    && unzip /kaitai-struct-compiler-${VERSION}.zip \
    && mv /kaitai-struct-compiler-${VERSION} /kaitai \
    && rm /kaitai-struct-compiler-${VERSION}.zip

ENTRYPOINT ["/kaitai-struct-compiler-0.8/bin/kaitai-struct-compiler"]
