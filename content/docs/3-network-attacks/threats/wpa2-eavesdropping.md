---
weight: 10
title: "WPA-2 Eavesdropping"
---

# WPA-2 Eavesdropping

## Personal WPA-2

*Personal* WPA-2 networks are prone to eavesdropping attacks. The attacker can authenticate with the network can capture all traffic.

This is possible because the router broadcasts the network the keycounter along with some other information. This broadcasted info along with the network password is used to generate the key.

If the attacker has the network password, they can generate the key and intercept all traffic.

## Enterprise WPA-2

*Enterprise* WPA-2 networks prevent eavesdropping attacks by using an Authentication server to authenticate users.

Once the client device is authenticated, it receives a unique encryption key that is used to encrypt all data transmitted between the client and the network.

This key is different for each client, and it is periodically changed to ensure the security of the network.
