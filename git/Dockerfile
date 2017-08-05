FROM alpine:latest

# docker run -it --rm \
#     -v $HOME/.ssh:/root/.ssh
#     -v $HOME/.git:/root/.git
#     -v $HOME/.gitconfig:/root/.gitconfig
#     -v /path/to/git/repo:/git \
#     --name git

# Fix ANSI color codes not escaped properly
ENV GIT_PAGER=

WORKDIR /git
RUN apk add --no-cache git openssh

ENTRYPOINT ["git"]
