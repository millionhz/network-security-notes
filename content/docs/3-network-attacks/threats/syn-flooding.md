---
weight: 30
title: "SYN Flooding"
---

# SYN Flooding

TCP SYN Flooding is a type of Denial of Service (DoS) attack in which an attacker sends a large number of SYN packets to a target system in an attempt to exhaust the system’s resources and prevent legitimate users from accessing the system.

## Three Way Handshake

Client and Server establish a connection by performing a *three way handshake*:

1. Client requests connection by sending SYN (synchronize) message to the server.
2. Server acknowledges by sending SYN-ACK (synchronize-acknowledge) message back to the client.
3. Client responds with an ACK (acknowledge) message, and the connection is established.

## SYN Flooding Workflow

1. The attacker sends repeated SYN packets to every port on the targeted server (often using a spoofed IP address).
2. The server, unaware of the attack, receives multiple, apparently legitimate requests to establish communication and replied with a SYN-ACK packet from each open port.
3. During this time, the server cannot close down the connection by sending an RST packet, and the connection stays open.
4. This leaves an increasingly large number of connections half-open.

Eventually, as the server’s connection overflow tables fill, service to legitimate clients will be denied.

{{<  hint info >}}
Spoofed IPs are used so ACK packets sent in reply to the SYN packets do not get sent to the attacker's machine.
{{< /hint >}}

## Defense against SYN Flooding

### SYN cookies

This strategy involves the creation of a cookie by the server. In order to avoid the risk of dropping connections when the backlog has been filled, the server responds to each connection request with a SYN-ACK packet but then drops the SYN request from the backlog, removing the request from memory and leaving the port open and ready to make a new connection.

If the connection is a legitimate request, and a final ACK packet is sent from the client machine back to the server, the server will then reconstruct (with some limitations) the SYN backlog queue entry.

While this mitigation effort does lose some information about the TCP connection, it is better than allowing denial-of-service to occur to legitimate users as a result of an attack.

### Recycling the Oldest Half-Open TCP connection

Once the backlog of half-open connections reaches a certain threshold, the oldest half-open connection is closed and the new connection is accepted.

This strategy requires that the legitimate connections can be fully established in less time than the backlog can be filled with malicious SYN packets. This particular defense fails when the attack volume is increased, or if the backlog size is too small to be practical.
