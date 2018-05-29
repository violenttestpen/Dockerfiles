FROM alpine:latest

# WORKDIR /root
# RUN apt-get update
# RUN apt-get install -y --no-install-recommends git python ca-certificates sudo
# RUN git clone https://github.com/LionSec/xerosploit.git
# #ENV PYTHONIOENCODING utf_8
# RUN cd xerosploit \
#     && echo 1 | python install.py

RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN apk add --no-cache nmap hping3 build-base ruby-dev libpcap-dev gmp-dev python2 py2-pip
RUN apk add --no-cache git ruby
RUN apk add --no-cache ruby-rdoc
RUN git clone https://github.com/LionSec/xerosploit.git
RUN cd xerosploit/tools/bettercap/ \
    && gem build bettercap.* \
    && gem install xettercap-* \
    && rm xettercap-* \
    && cd ../../ \
    && mkdir -p /opt/xerosploit \
    && cp -R tools/ /opt/xerosploit \
    && cp xerosploit.py /opt/xerosploit/xerosploit.py \
    && cp banner.py /opt/xerosploit/banner.py \
    && cp run.sh /usr/bin/xerosploit \
    && chmod +x /usr/bin/xerosploit \
    && tput setaf 34

ENTRYPOINT ["xerosploit"]
