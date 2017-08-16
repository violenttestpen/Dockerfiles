FROM alpine:latest

WORKDIR /root
RUN apk add --no-cache wget g++ make linux-headers \
    && wget --no-check-certificate https://github.com/drk1wi/portspoof/archive/master.tar.gz -O - | tar xz \
    # Compile and install
    && cp /usr/include/linux/sysctl.h /usr/include/sys/sysctl.h \
    && (cd portspoof-master \
        && ./configure \
        && make -j \
        && make install) \
    # Cleanup
    && apk del --purge wget make linux-headers

ENTRYPOINT ["portspoof"]
CMD ["-h"]
