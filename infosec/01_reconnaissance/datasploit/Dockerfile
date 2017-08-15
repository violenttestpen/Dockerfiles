FROM alpine:latest

WORKDIR /root
RUN apk add --no-cache python wget py-pip python-dev g++ libxml2-dev libxslt-dev \
    && wget --no-check-certificate https://github.com/DataSploit/datasploit/archive/master.tar.gz -O - | tar xz \
    # Install dependencies
    && pip install --no-cache-dir -r datasploit-master/requirements.txt \
    && cp datasploit-master/config_sample.py datasploit-master/config.py \
    # Cleanup
    && apk del --purge wget python-dev g++ libxml2-dev libxslt-dev

ENTRYPOINT ["python", "/root/datasploit-master/datasploit.py"]
CMD ["-h"]
