FROM debian:stretch-slim

WORKDIR /root
#RUN apt-get update \
    # Add Kali official repository
#    && apt-get install -y --no-install-recommends gnupg2 dirmngr \
#    && apt-key adv --keyserver hkp://keys.gnupg.net --recv-keys ED444FF07D8D0BF6 \
#    && echo 'deb http://http.kali.org/kali kali-rolling main contrib non-free' >> /etc/apt/sources.list \
RUN echo 'deb http://http.kali.org/kali kali-rolling main contrib non-free' >> /etc/apt/sources.list \
    && echo 'APT::Get::AllowUnauthenticated "true";' >> /etc/apt/apt.conf.d/99-allow-unauthenticated \
    # Install external dependencies
    && apt-get update \
    && apt-get install -y --no-install-recommends net-tools ca-certificates curl git python-pip build-essential \
    # Install Sn1per
    && git clone https://github.com/1N3/Sn1per.git \
    && (cd Sn1per && chmod +x install.sh && yes | ./install.sh) \
    # Cleanup
    && apt-get purge -y git python-pip build-essential \
    && apt-get autoremove -y \
    && rm -rf /var/lib/apt/lists/* Sn1per ~/.cache

ENTRYPOINT ["/usr/bin/sniper"]
CMD ["--help"]
