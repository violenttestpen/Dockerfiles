FROM alpine:latest

# Install the magic wrapper.
COPY ./wrapdocker /usr/local/bin/wrapdocker

# Install Docker and dependencies
RUN apk --no-cache add \
        bash \
        iptables \
        ca-certificates \
        e2fsprogs \
        docker \
    && chmod +x /usr/local/bin/wrapdocker

# Define additional metadata for our image.
VOLUME /var/lib/docker
CMD ["wrapdocker"]