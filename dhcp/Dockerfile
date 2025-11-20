FROM ubuntu:22.04

# Install DHCP server
RUN apt-get update && apt-get install -y isc-dhcp-server iproute2 iputils-ping \
    && mkdir -p /var/lib/dhcp \
    && touch /var/lib/dhcp/dhcpd.leases \
    && chmod 664 /var/lib/dhcp/dhcpd.leases \
    && apt-get clean

COPY dhcpd.conf /etc/dhcp/dhcpd.conf

EXPOSE 67/udp

# Keep container alive even if dhcpd fails
CMD ["bash", "-c", "dhcpd -f -4 || tail -f /dev/null"]
