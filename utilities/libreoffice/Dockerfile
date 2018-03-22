FROM alpine:latest

RUN apk add --no-cache \
    libreoffice \
    ttf-dejavu \
    dbus

RUN adduser libreoffice -D
USER libreoffice
ENTRYPOINT ["libreoffice"]
