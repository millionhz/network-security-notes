---
weight: 20
title: "RST Injection"
---

# RST Injection

RST Injection is a Denial of Service (DoS) attack which can be used to disrupt the normal operation of a TCP connection between two hosts.

## RST Injection Workflow

Normally, a TCP connection is closed by each side sending a **FIN packet** which is reliably delivered with ACKs.

However, if a process terminates without closing the connection, the operating system can send a RST packet to terminate the connection. **RST packets** are unilateral and dont require acks. However they are only accepted by the peer if **correct sequence numbers** are used.

If the attacker knows the **port number** and **sequence number** of the connection, they can send a RST packet to terminate the connection forcefully.

## Defenses Against RST Injection

### TCP Sequence Number Randomization

The attacker needs to know the correct sequence number in order to carry out a RST injection attack. If the sequence number is randomized, the attacker will not be able to accurately guess the sequence number of a legitimate connection.
