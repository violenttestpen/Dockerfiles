FROM debian:stretch-slim

WORKDIR /root
RUN apt-get update \
#    && apt-get install -y --no-install-recommends wget python \
    && apt-get install -y --no-install-recommends wget \
    && wget --no-check-certificate https://github.com/pts/staticpython/raw/master/release/python2.7-static -O /usr/bin/python \
    && chmod +x /usr/bin/python \
    # Download Dropbox binaries
    && wget --no-check-certificate "https://www.dropbox.com/download?plat=lnx.x86_64" -O - | tar xz \
    && wget --no-check-certificate "https://www.dropbox.com/download?dl=packages/dropbox.py" -O /usr/bin/dropbox \
    && chmod +x /usr/bin/dropbox \
    # Cleanup
    && apt-get remove --purge -y wget \
    && apt-get -y autoremove \
    && apt-get clean \
    && rm -rf /tmp/* /var/tmp/* /var/cache/apt/archives/* /var/lib/apt/lists/* \
    # Create Dropbox directory
    && mkdir -p /root/Dropbox

COPY run.sh /root/run.sh
VOLUME ["/root/Dropbox", "/root/.dropbox"]

ENTRYPOINT ["/root/run.sh"]
