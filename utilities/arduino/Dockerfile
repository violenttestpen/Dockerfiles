FROM ubuntu:latest

# ARDUINO_VERSION = '1.x.x'
ARG ARDUINO_VERSION

WORKDIR /root
RUN apt-get update \
    && apt-get install -y --no-install-recommends openjdk-8-jdk libusb-0.1-4 gcc wget xz-utils \
    && wget --no-check-certificate https://downloads.arduino.cc/arduino-${ARDUINO_VERSION}-linux64.tar.xz -O - | tar xJ \
    && bash /root/arduino-${ARDUINO_VERSION}/install.sh \
    && apt-get purge -y --autoremove wget xz-utils \
    && rm -rf /var/cache/apt/lists/*

WORKDIR /root/arduino-${ARDUINO_VERSION}
ENTRYPOINT ["/bin/bash", "arduino"]
