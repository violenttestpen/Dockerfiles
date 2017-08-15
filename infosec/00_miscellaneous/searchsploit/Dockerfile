FROM alpine:latest

WORKDIR /root
RUN apk add --no-cache bash ncurses libxml2-utils wget \
    && wget --no-check-certificate https://github.com/offensive-security/exploit-database/archive/master.tar.gz -O - | tar xz \
    # Initialize
    && mkdir -p /opt/exploit-database \
    && mv exploit-database-master/files.csv /opt/exploit-database \
    # Cleanup
    && apk del --purge wget

ENTRYPOINT ["/root/exploit-database-master/searchsploit"]
