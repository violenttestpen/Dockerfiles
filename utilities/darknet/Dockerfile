FROM alpine:latest AS staging

WORKDIR /app

RUN apk update
RUN apk add git build-base
RUN git clone https://github.com/pjreddie/darknet.git /app

RUN make

FROM alpine:latest

WORKDIR /app
COPY --from=staging /app/darknet /app/darknet
COPY --from=staging /app/libdarknet.* /app/libdarknet.*
COPY --from=staging /app/cfg/coco.data /app/cfg/coco.data
COPY --from=staging /app/cfg/yolov3.cfg /app/cfg/yolov3.cfg
COPY --from=staging /app/data/labels/* /app/data/labels/*
COPY --from=staging /app/data/coco.names /app/data/coco.names

ENTRYPOINT ["darknet"]