FROM alpine:latest

ENV DISPLAY=:0.0 \
    DISPLAY_WIDTH=1024 \
    DISPLAY_HEIGHT=768

# x11vnc is in testing repo
RUN echo "http://dl-cdn.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories \
    # Install git, supervisor, VNC, & X11 packages
    && apk --no-cache add \
        bash \
        git \
        supervisor \
        # xterm (optional)
        xterm \
        # fluxbox for minimal Desktop Environment, replace when necessary
        fluxbox \
        # xvfb to provide virtual X11 frame buffering, x11vnc as VNC server
        x11vnc \
        xvfb \
        # socat to allow inter-container VNC
        # socat \
    # Clone noVNC from github
    && git clone https://github.com/kanaka/noVNC.git /root/noVNC \
    # Clone websockify first so that we can uninstall git safely
    && git clone https://github.com/kanaka/websockify /root/noVNC/utils/websockify \
    && rm -rf /root/noVNC/.git /root/noVNC/utils/websockify/.git \
    && apk del --purge git

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

# Modify the launch script 'ps -p'
# RUN sed -i -- "s/ps -p/ps -o pid | grep/g" /root/noVNC/utils/launch.sh

EXPOSE 8080

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]
