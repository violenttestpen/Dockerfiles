FROM alpine:latest AS staging

RUN apk add --no-cache git
RUN git clone https://github.com/neoneggplant/EggShell.git /EggShell

FROM alpine:latest

RUN apk add --no-cache python2 py2-crypto
COPY --from=staging /EggShell /EggShell

WORKDIR /EggShell
ENTRYPOINT ["python", "/EggShell/eggshell.py"]
