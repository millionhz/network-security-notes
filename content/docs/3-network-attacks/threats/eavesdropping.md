---
weight: 10
title: "Eavesdropping"
---

# Eavesdropping

Eavesdropping, also knows as *sniffing*,  refers to the unauthorized interception and monitoring of network traffic.

Any system with an NIC (Network Interface Card) can capture communication over a subnet using tools like `tcpdump` or [Wireshark](https://www.wireshark.org/).

Alternatively, logged traffic can be exported from routers and switches or from a network tap.

# WPA-2 Eavesdropping

## Personal WPA-2

*Personal* WPA-2 networks are prone to eavesdropping attacks. The attacker can authenticate with the network can capture all traffic.

This is possible because the router broadcasts the network the keycounter along with some other information. This broadcasted info along with the network password is used to generate the key. If the attacker has the network password, they can generate the key.

## Enterprise WPA-2

*Enterprise* WPA-2 networks prevent eavesdropping attacks by using an Authentication server to authenticate users. Once the client device is authenticated, it receives a unique encryption key that is used to encrypt all data transmitted between the client and the network. This key is different for each client, and it is periodically changed to ensure the security of the network.
