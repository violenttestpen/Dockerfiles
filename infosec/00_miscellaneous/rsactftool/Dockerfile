FROM alpine:latest

WORKDIR /root
RUN apk add --no-cache python3 gmp mpfr3 mpc1 py3-pip git g++ python3-dev gmp-dev mpfr-dev mpc1-dev \
    && git clone https://github.com/Ganapati/RsaCtfTool.git . \
    && pip3 install --no-cache-dir -r requirements.txt \
    && pip3 install --no-cache-dir -r optional-requirements.txt \
    && apk del --purge py3-pip git g++ python3-dev gmp-dev mpfr-dev mpc1-dev

ENTRYPOINT ["/root/RsaCtfTool.py"]
CMD ["-h"]
