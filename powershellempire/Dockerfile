FROM ubuntu:16.04

WORKDIR /root
RUN apt-get update && \
    apt-get install --no-install-recommends -y git
RUN env GIT_SSL_NO_VERIFY=true git clone https://github.com/EmpireProject/Empire.git
RUN cd Empire && \
    bash setup/install.sh && \
    apt-get purge make g++ python-dev libxml2-dev libssl-dev && \
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["/root/Empire/empire"]
