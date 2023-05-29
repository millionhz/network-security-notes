---
weight: 20
title: "Network Attacks"
bookCollapseSection: true
---
# Types Network Attacks

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

# Attacks

## Physical/Link - Layer 1/2 Attacks

- [WPA-2 Eavesdropping]({{< relref "/wpa2-eavesdropping.md" >}})
- [DHCP Spoofing]({{< relref "/dhcp-spoofing.md" >}})
- ARP Poisoning

## Network/IP Layer - Layer 3 Attacks

- IP Spoofing
- MITM Attacks

## Transport/TCP Layer - Layer 4 Attacks

- [RST Injection]({{< relref "/rst-injection.md" >}})
- [TCP Spoofing/Session Hijacking]({{< relref "/tcp-spoofing.md" >}})
- [SYN Flooding]({{< relref "/syn-flooding.md" >}})

## DNS Attacks

- [DNS Cache Poisoning]({{< relref "/dns-cache-poisoning.md" >}})
