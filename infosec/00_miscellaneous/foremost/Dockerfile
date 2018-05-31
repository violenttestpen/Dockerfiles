FROM alpine:latest

RUN apk add --no-cache git gcc make libc-dev \
    && git clone https://github.com/DogFive/foremost.git \
    && (cd /foremost && make && make install) \
    && rm -rf /foremost \
    && apk del --purge git gcc make libc-dev
