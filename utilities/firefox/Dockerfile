FROM alpine:latest

RUN apk add --no-cache \
        dbus \
        mesa-gl \
        ttf-freefont \
        hicolor-icon-theme \
        ca-certificates \
        firefox-esr

RUN adduser firefox -D \
    && adduser firefox audio \
    && adduser firefox video \
    && chown -R firefox:firefox /home/firefox

USER firefox

ENTRYPOINT ["/usr/bin/firefox"]
