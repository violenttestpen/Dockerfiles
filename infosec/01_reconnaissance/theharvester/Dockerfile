FROM alpine:latest

RUN apk add --no-cache python2 py2-requests git \
    && git clone https://github.com/laramies/theHarvester.git /theHarvester \
    && rm -rf /theHarvester/.git \
    && apk del --purge git

ENTRYPOINT ["/usr/bin/python", "/theHarvester/theHarvester.py"]
