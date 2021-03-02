FROM debian:latest

RUN dpkg --add-architecture i386
RUN apt-get update \
    # Install compilation tools and gdb
    && apt-get install -y dpkg-dev gcc-multilib gdb \
    # Install python 2 and 3
    && apt-get install -y python2.7 python3 python-pip python3-pip \
    # Install git
    && apt-get install -y git \
    # Add missing ps
    && apt-get install -y procps \
    # Add missing netstat
    && apt-get install -y net-tools \
    # Cleanup
    && rm -rf /var/cache/apt/*

# Install pwntools
RUN pip install --no-cache-dir pwntools \
    && pip3 install --no-cache-dir pwntools

RUN mkdir -p /opt/protostar/run
RUN useradd user -m \
    && echo "user:user" | chpasswd \
    && chsh -s /bin/bash user

# Install gef
ADD --chown=user:user http://gef.blah.cat/py /home/user/.gdbinit-gef.py
RUN pip3 install --no-cache-dir keystone-engine ropper
RUN echo source /home/user/.gdbinit-gef.py >> /home/user/.gdbinit \
    && chmod +x /home/user/.gdbinit-gef.py
RUN echo "export LC_CTYPE=C.UTF-8" >> /home/user/.bashrc

COPY protostar/ /opt/protostar/bin
COPY rc.local /etc/rc.local

EXPOSE 2993-2999
ENTRYPOINT ["/etc/rc.local"]
CMD ["/bin/bash"]
