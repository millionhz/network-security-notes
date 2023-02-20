---
weight: 30
title: "Network Attacks"
---

# Network Attacks

## Eavesdropping

Eavesdropping, also knows as *sniffing*,  refers to the unauthorized interception and monitoring of network traffic.

Any system with an NIC (Network Interface Card) can capture communication over a subnet using tools like `tcpdump` or [Wireshark](https://www.wireshark.org/).

Alternatively, logged traffic can be exported from routers and switches or from a network tap.

## Spoofing

Spoofing in network security is the act of impersonating another user, device, or network in order to gain unauthorized access, steal information, or launch an attack.

This is especially powerful when combined with eavesdropping. The attacker can retrieve the exact state of the victim's communication and craft their spoofed traffic to match it.

{{<  hint info >}}
Spoofing without eavesdropping is called *blind-spoofing*
{{< /hint >}}

# Network Layers

| # | Layer | Description |
| - | ----- | ----------- |
| 7 | Application Layer | This layer is responsible for providing access to network services and communication between user applications. |
| 6 | Presentation layer | - |
| 5 | Session Layer | - |
| 4 | Transport Layer | This layer is responsible for the end-to-end delivery of data between two hosts. It provides error detection and correction, flow control, and fragmentation and reassembly of data packets.  |
| 3 | Network layer | This layer is responsible for the logical addressing and routing of data between different networks. It determines the best path for data to travel between networks and handles congestion control. |
| 2 | Data link layer| This layer is responsible for the reliable transmission of data over the physical layer. It is responsible for error detection and correction, flow control, and framing.|
| 1 | Physical | The physical layer is responsible for the physical transmission of data over a network. It defines the hardware and physical characteristics of the network, such as cables, connectors, and signal types. |
