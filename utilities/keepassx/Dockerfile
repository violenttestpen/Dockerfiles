FROM alpine:latest

# docker run -d \
#     -v $HOME:/root \
#     -v /tmp/.X11-unix:/tmp/.X11-unix \
#     -e DISPLAY=unix$DISPLAY \

RUN apk add --no-cache \
    keepassx \
    ttf-dejavu

ENTRYPOINT ["keepassx"] 
