FROM alpine:latest

RUN apk add --no-cache git gcc make libc-dev \
    && git clone https://github.com/DogFive/foremost.git \
    && (cd /foremost && make && make install) \
    # Fixed an issue regarding foremost.conf
    && rm -f /usr/local/etc \
    && mkdir -p /usr/local/etc \
    && cp /foremost/foremost.conf /usr/local/etc/ \
    # Cleanup
    && rm -rf /foremost \
    && apk del --purge git gcc make libc-dev

ENTRYPOINT ["foremost"]
