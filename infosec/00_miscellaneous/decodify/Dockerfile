FROM alpine:latest

ADD https://raw.githubusercontent.com/UltimateHackers/Decodify/master/dcode /usr/local/bin/dcode
RUN apk add --no-cache python2 \
    && chmod +x /usr/local/bin/dcode
ENTRYPOINT ["dcode"]
