FROM alpine:latest

WORKDIR /root
RUN apk add --no-cache python gmp py-pip git g++ python-dev gmp-dev \
    && git clone https://github.com/Ganapati/RsaCtfTool.git . \
    && pip install --no-cache-dir -r requirements.txt \
    && pip install --no-cache-dir git+https://github.com/hellman/libnum \
    && apk del --purge py-pip git g++ python-dev gmp-dev

ENTRYPOINT ["/root/RsaCtfTool.py"]
CMD ["-h"]
