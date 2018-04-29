FROM ubuntu:latest

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update \
    && apt-get install -y wget libgtk2.0.0 libxtst6 libxss1 libgconf2-4 libnss3 libasound2 \
    && wget http://pencil.evolus.vn/dl/V3.0.4/Pencil_3.0.4_amd64.deb -O /tmp/Pencil_3.0.4_amd64.deb \
    && dpkg -i /tmp/Pencil_3.0.4_amd64.deb \
    && rm /tmp/Pencil_3.0.4_amd64.deb \
    && apt-get purge -y wget \
    && apt-get autoremove -y \
    && apt-get clean
ENTRYPOINT ["pencil"]