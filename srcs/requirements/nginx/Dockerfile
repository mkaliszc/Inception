FROM alpine:3.21.2

RUN apk update --no-cache && apk add --no-cache openssl nginx

RUN mkdir -p /var/www/wordpress /etc/nginx/ssl /run/nginx

RUN openssl req -newkey rsa:2048 -nodes \
    -keyout /etc/nginx/ssl/inception.key \
    -x509 -days 365 \
    -out /etc/nginx/ssl/inception.crt \
    -subj "/C=FR/L=Le Havre/O=42 Le Havre/OU=42/CN=${DOMAIN_NAME}/UID=mkaliszc"	

COPY conf/nginx.conf /etc/nginx/nginx.conf

EXPOSE 443

CMD ["nginx", "-g", "daemon off;"]