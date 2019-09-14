FROM alpine:latest

ENV VERSION v9.7.1

WORKDIR /app
RUN apk add --no-cache apache2 \
    && wget -O /tmp/CyberChef.zip "https://github.com/gchq/CyberChef/releases/download/$VERSION/CyberChef_$VERSION.zip" \
    && unzip -d /var/www/localhost/htdocs /tmp/CyberChef.zip \
    && rm -f /tmp/CyberChef.zip

EXPOSE 80

ENTRYPOINT ["httpd", "-D", "FOREGROUND"]