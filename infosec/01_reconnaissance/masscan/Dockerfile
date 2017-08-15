FROM alpine:latest

WORKDIR /root
RUN apk add --no-cache wget g++ make libpcap-dev linux-headers \
    # Download and compile binary
    && wget --no-check-certificate https://github.com/robertdavidgraham/masscan/archive/master.tar.gz -O - | tar xz \
    && (cd masscan-master && make -j) \
    # Post-install
    && cp masscan-master/bin/masscan /usr/local/bin/masscan \
    # Cleanup
    && rm -rf masscan-master \
    && apk del --purge wget g++ make linux-headers

ENTRYPOINT ["masscan"]
