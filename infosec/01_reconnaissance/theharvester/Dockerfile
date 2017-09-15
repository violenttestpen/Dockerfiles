FROM alpine:latest AS staging

# Download the repository
RUN apk add --no-cache git
RUN git clone https://github.com/laramies/theHarvester.git /root/theHarvester

FROM alpine:latest

COPY --from=staging /root/theHarvester /root/theHarvester
RUN apk add --no-cache python2 py2-requests

ENTRYPOINT ["/usr/bin/python", "/root/theHarvester/theHarvester.py"]
