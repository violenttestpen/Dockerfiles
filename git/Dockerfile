FROM alpine:latest

# docker run -it --rm \
#     -v $HOME/.git:/root/.git
#     -v /path/to/git/repo:/git \
#     --name git

WORKDIR /git
RUN apk add --no-cache \
    ca-certificates \
    git \
    openssh

ENTRYPOINT ["git"]
