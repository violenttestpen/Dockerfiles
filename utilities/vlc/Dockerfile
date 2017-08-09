FROM alpine:latest

RUN apk add --no-cache \
        vlc \
        dbus-libs \
        dbus-x11 \
        libxcb \
        libxv \
        mesa-dri-ati \
        mesa-dri-intel \
        mesa-dri-nouveau \
        mesa-dri-swrast \
        mesa-dri-vmwgfx \
        ttf-freefont \
        vlc-qt \
        alsa-utils \
    && dbus-uuidgen --ensure=/etc/machine-id \
    && ln -sf /etc/machine-id /var/lib/dbus/machine-id
RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN apk add --no-cache pulseaudio
RUN sed -i 's/geteuid/getppid/' /usr/bin/vlc

RUN adduser pulse -D
USER user
ENTRYPOINT ["vlc"]
