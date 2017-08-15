FROM alpine:latest

WORKDIR /root
RUN apk add --no-cache python py-requests wget \
    # Download the repository
    && wget --no-check-certificate https://github.com/laramies/theHarvester/archive/master.tar.gz -O - | tar xz \
    # Cleanup
    && apk del --purge wget

ENTRYPOINT ["python", "/root/theHarvester-master/theHarvester.py"]
