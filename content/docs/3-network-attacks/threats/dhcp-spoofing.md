---
weight: 20
title: "DHCP Spoofing"
---

# DHCP

A new host does not have an IP Address nor do they know who to ping to get an IP address. So the host sends a broadcast message to the network asking for an IP address.

The DHCP server receives this message and responds with a DHCP offer which contains:

| DHCP Offer | Description |
| --- | --- |
| IP Address |  IP Address for the machine |
| DNS Address | Address of server used to map hostnames to IPs |
| Gateway Address | IP address of the router which is used as the first hop  |

## DHCP Spoofing

An attacker on the same subnet can listen for new hosts and race the actual the DHCP server to respond to the new host.

If the attacker wins, it can send a malicious DHCP offer to the new host.

## DHCP Threats

### Fake DNS

Redirect any of the host's DNS requests to a malicious DNS server.

### Fake Gateway

Intercept the host's off-subnet traffic and rely content back and forth between the host and remote server (*invisible* Man In The Middle).

## Preventions

### DHCP snooping

DHCP snooping works by allowing a network switch to inspect and validate DHCP messages that are sent between DHCP clients and servers.

When a switch has DHCP snooping enabled, it maintains a database of all DHCP clients and servers on the network. It then compares incoming DHCP messages to this database to determine if they are legitimate or not. If a message is determined to be illegitimate, the switch will drop it before it can reach the intended recipient.
