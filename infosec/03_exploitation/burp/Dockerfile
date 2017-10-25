FROM ubuntu:17.04

RUN apt-get update \
    && apt-get install -y --no-install-recommends openjdk-8-jre \
    && rm -rf /var/lib/apt/lists/*

ADD https://portswigger.net/DownloadUpdate.ashx?Product=Free /root/burpsuite.jar

CMD ["java", "-jar", "/root/burpsuite.jar"]
