FROM ubuntu:latest

ENV ANDROID_DOWNLOAD_URL https://dl.google.com/dl/android/studio/ide-zips/3.1.3.0/android-studio-ide-173.4819257-linux.zip

RUN dpkg --add-architecture i386 \
    && apt-get update \
    && apt-get install -y \
        # Install Google's recommended dependencies
        libc6:i386 \
        libncurses5:i386 \
        libstdc++6:i386 \
        lib32z1 \
        libbz2-1.0:i386 \
        # Install missing dependencies required to work
        libxext6 \
        libxrender1 \
        libxtst6 \
        libxi6 \
        libfreetype6 \
        # Install miscellaneous tools
        wget \
        unzip \
    && wget $ANDROID_DOWNLOAD_URL -O /tmp/android.zip \
    && unzip /tmp/android.zip -d /usr/local \
    # Cleanup
    && apt-get purge -y wget unzip \
    && rm -rf /tmp/android.zip /var/cache/apt/*

CMD ["/usr/local/android-studio/bin/studio.sh"]
