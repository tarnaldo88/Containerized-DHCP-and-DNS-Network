FROM ubuntu:22.04

RUN apt update && apt install -y isc-dhcp-server

COPY dhcpd.conf /etc/dhcp/dhcpd.conf

EXPOSE 67/udp

CMD ["dhcpd", "-f", "-4"]
