FROM debian:stretch-slim

# docker run --rm -it \
#   --net host \
#   -v /tmp/.X11-unix:/tmp/.X11-unix \
#   -e DISPLAY=unix$DISPLAY \
#   --device /dev/dri \
#   --device /dev/snd \
#   -v /dev/shm:/dev/shm \
#   -v /etc/fonts:/etc/fonts \
#   -v /etc/machine-id:/etc/machine-id \
#   -v /usr/share/fonts:/usr/share/fonts \
#   -v $HOME/.config/midori:/root/.config/midori \
#   --ipc="host" \
#   --name midori \

RUN apt-get update \
	&& apt-get install -y --no-install-recommends midori ca-certificates \
	&& rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["midori"]
