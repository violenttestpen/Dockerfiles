FROM alpine:latest

WORKDIR /root/Empire

# Install git for cloning repository (apk add openjdk8 if need to use java)
RUN apk add --no-cache git python bash linux-headers make g++ python-dev swig py-pip libxml2-dev libffi-dev libressl-dev \
    && env GIT_SSL_NO_VERIFY=true git clone https://github.com/EmpireProject/Empire.git . \
    # Setup, echo for accepting setup_database.py prompt
    && echo | bash setup/install.sh \
    && pip install m2crypto \
    # Cleanup
    && rm -rf /root/.cache \
    && apk del --purge git bash linux-headers make g++ python-dev libxml2-dev libffi-dev libressl-dev

ENTRYPOINT ["./empire"]
