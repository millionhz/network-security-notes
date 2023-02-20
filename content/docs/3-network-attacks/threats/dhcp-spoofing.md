---
weight: 20
title: "DHCP Spoofing"
---

# DHCP

A new host does not have an IP Address nor do they who to ping to get an IP address. So the host sends a broadcast message to the network asking for an IP address.

The DHCP server receives this message and responds with a DHCP offer which contains:

- IP address
- DNS server - used to map hostnames to IP Addresses
- Gateway address - IP address of the router that client uses as the first hop for all its internet traffic

## DHCP Spoofing

An attacker on the same subnet can listen for new hosts and race the actual the DHCP server to respond to the new host.

If the attacker wins, it can send a malicious DHCP offer to the new host.

## DHCP Threats

### Fake DNS

Redirect any of the host's DNS requests to a malicious DNS server.

### Fake Gateway

Intercept of the host's off-subnet traffic and rely contents back and forth between the host and remote server (*invisible* Man In The Middle).
