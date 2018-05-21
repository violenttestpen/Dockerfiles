FROM alpine:latest

RUN apk add --no-cache git bash ncurses nmap xterm proxychains-ng \
    && git clone --recursive https://github.com/trimstray/sandmap /sandmap \
    && chmod +x /sandmap/setup.sh \
    && /sandmap/setup.sh install \
    && apk del --purge git

ENTRYPOINT ["sandmap"]
