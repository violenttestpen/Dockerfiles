FROM alpine:latest

RUN apk add --no-cache nodejs nodejs-npm \
    && npm install -g localtunnel

ENTRYPOINT ["lt"]