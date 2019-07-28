FROM alpine:latest AS staging

RUN apk add --no-cache \
	python3 \
	py3-pip \
	py3-cffi \
	python3-dev \
	libressl-dev \
	build-base

RUN pip3 install mitmproxy

FROM alpine:latest

ENV LANG en_US.UTF-8

COPY --from=staging /usr/lib/python3.6/site-packages /usr/lib/python3.6/site-packages
COPY --from=staging /usr/bin/mitm* /usr/bin/

RUN apk add --no-cache \
	python3 \
	libressl

EXPOSE 8080

CMD ["/usr/bin/mitmdump"]
