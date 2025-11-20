FROM ubuntu:22.04

# Install DHCP server
RUN apt-get update && apt-get install -y isc-dhcp-server iproute2 iputils-ping \
    && apt-get clean

# Copy your DHCP config
COPY dhcpd.conf /etc/dhcp/dhcpd.conf

# Expose DHCP port
EXPOSE 67/udp

# Run DHCP in foreground
CMD ["dhcpd", "-f", "-4"]
