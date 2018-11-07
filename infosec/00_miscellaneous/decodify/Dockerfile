FROM alpine:latest

ADD https://raw.githubusercontent.com/UltimateHackers/Decodify/master/dcode /usr/local/bin/dcode
RUN wget https://github.com/pts/staticpython/raw/master/release/python2.7-static -O /usr/local/bin/python2 \
    && ln -s /usr/local/bin/python2 /usr/local/bin/python \
    && chmod +x /usr/local/bin/python2 \
    && chmod +x /usr/local/bin/dcode
ENTRYPOINT ["dcode"]
