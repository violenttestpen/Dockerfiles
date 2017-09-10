FROM alpine:latest

RUN apk add --no-cache \
    dbus \
    mesa-gl \
    ttf-freefont \
    hicolor-icon-theme \
    ca-certificates \
    firefox-esr

ENTRYPOINT ["/usr/bin/firefox"]
