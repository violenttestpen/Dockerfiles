FROM alpine:latest

RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN apk update
RUN apk add \
        vlc \
#        dbus-libs \
#        dbus-x11 \
#        libxcb \
#        libxv \
#        mesa-dri-ati \
#        mesa-dri-intel \
#        mesa-dri-nouveau \
#        mesa-dri-swrast \
#        mesa-dri-vmwgfx \
#        ttf-freefont \
        vlc-qt \
        vlc-xorg
RUN apk add pulseaudio-alsa
#    && dbus-uuidgen --ensure=/etc/machine-id \
#    && ln -sf /etc/machine-id /var/lib/dbus/machine-id
#RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
#RUN apk add --no-cache pulseaudio
#RUN sed -i 's/geteuid/getppid/' /usr/bin/vlc

ENV HOME /home/vlc
RUN adduser vlc -H $HOME -D \
    && adduser vlc audio \
    && adduser vlc video
USER vlc

ENTRYPOINT ["vlc"]
