FROM ubuntu:22.04

RUN apt update && apt install -y bind9 bind9utils bind9-dnsutils

COPY named.conf /etc/bind/named.conf
COPY db.test.local /etc/bind/db.test.local

EXPOSE 53/udp
EXPOSE 53/tcp

CMD ["named", "-g"]
