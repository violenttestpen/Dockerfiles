FROM alpine:latest AS staging

RUN apk add --no-cache python2 py2-pip python2-dev g++ make bash git ncurses-dev
RUN git clone https://github.com/D4Vinci/One-Lin3r.git /root/One-Lin3r
RUN pip install --no-cache-dir -r /root/One-Lin3r/requirements.txt

FROM alpine:latest

RUN apk add --no-cache python2

COPY --from=staging /usr/lib/python2.7/site-packages /usr/lib/python2.7/site-packages
COPY --from=staging /root/One-Lin3r /root/One-Lin3r

WORKDIR /root/One-Lin3r
ENTRYPOINT ["/usr/bin/python"]
CMD ["One_Lin3r.py"]
