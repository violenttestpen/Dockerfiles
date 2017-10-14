FROM alpine:latest AS staging

RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/main >> /etc/apk/repositories
RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN apk update
RUN apk add git python2 py2-pip py-prettytable py2-mako py2-yaml py2-dateutil
RUN pip install PySocks
RUN git clone https://github.com/epinna/weevely3 /weevely3 \
    && rm -rf /weevely3/.git

FROM alpine:latest

COPY --from=staging /usr/lib/python2.7/site-packages /usr/lib/python2.7/site-packages
COPY --from=staging /weevely3 /weevely3

RUN apk add --no-cache python2
RUN ln -s /weevely3/weevely.py /usr/local/bin/weevely

ENTRYPOINT ["weevely"]
