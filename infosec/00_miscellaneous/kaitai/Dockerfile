FROM alpine:latest

ENV VERSION 0.8

RUN apk add --no-cache \
        # Required for kaitai-struct-compiler
        bash \
        openjdk8-jre-base \
        # Required for kaitai-struct-visualizer
        ncurses \
        ruby \
        ruby-json \
        ruby-io-console \
    # Install kaitai-struct-compiler & kaitai-struct-visualizer
    && gem install --no-ri --no-rdoc kaitai-struct-visualizer \
    && wget https://dl.bintray.com/kaitai-io/universal/${VERSION}/kaitai-struct-compiler-${VERSION}.zip \
    && unzip /kaitai-struct-compiler-${VERSION}.zip \
    && mv /kaitai-struct-compiler-${VERSION} /kaitai \
    && rm /kaitai-struct-compiler-${VERSION}.zip \
    # Create relevant shortcuts for normal use
    && ln -s /kaitai/bin/kaitai-struct-compiler /usr/local/bin/kaitai-struct-compiler \
    && ln -s /kaitai/bin/kaitai-struct-compiler /usr/local/bin/ksc

ENTRYPOINT ["/usr/bin/ksv"]