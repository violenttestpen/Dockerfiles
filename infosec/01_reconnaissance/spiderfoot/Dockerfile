FROM alpine:latest

# docker run -p80:5001 spiderfoot
# docker run -p80:5001 --entrypoint /root/spiderfoot-master/sfcli.py spiderfoot

WORKDIR /root
RUN apk add --no-cache python swig libxslt wget python-dev py-pip g++ libressl-dev libxml2-dev libxslt-dev \
    && wget --no-check-certificate https://github.com/smicallef/spiderfoot/archive/master.tar.gz -O - | tar xz \
    && pip install --no-cache-dir -r spiderfoot-master/requirements.txt \
    # Fix M2Crypto module import error
    && pip install --no-cache-dir M2Crypto -U \
    # Cleanup
    && apk del --purge wget python-dev py-pip g++ libressl-dev libxml2-dev libxslt-dev

WORKDIR /root/spiderfoot-master
EXPOSE 5001
ENTRYPOINT ["./sf.py"]
CMD ["0.0.0.0:5001"]
