FROM ubuntu:16.04

WORKDIR /root/Empire
RUN apt-get update && \
    # Install git for cloning repository
    apt-get install --no-install-recommends -y git && \
    env GIT_SSL_NO_VERIFY=true git clone https://github.com/EmpireProject/Empire.git . && \
    # Setup, echo for accepting setup_database.py prompt
    echo | bash setup/install.sh && \
    # Cleanup
    apt-get purge -y make g++ python-dev python-pip libxml2-dev libssl-dev && \
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["./empire"]
