FROM alpine:latest

WORKDIR /root
RUN apk add --no-cache python py-requests wget && \
    # Download the repository
    wget --no-check-certificate https://github.com/laramies/theHarvester/archive/master.tar.gz && \
    tar xzf master.tar.gz && \
    # Cleanup
    apk del --purge wget && \
    rm -f master.tar.gz

ENTRYPOINT ["python", "/root/theHarvester-master/theHarvester.py"]
