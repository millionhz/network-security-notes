---
weight: 30
title: "Firewall"
---

# Firewall

## Whitelist Approach

The motivation for using firewalls as a whitelist approach is to enhance the security of a network by explicitly allowing only known and trusted traffic to enter or leave the network.

With a whitelist approach, traffic is only allowed based on pre-defined rules, which can greatly reduce the risk of unauthorized access, data breaches, and other security threats.

## Packet Filtering

A firewall can be configured to act as a packet filter, which means that it examines each packet of data that passes through the firewall and decides whether to allow or block it based on a set of predefined rules.

These rules are typically based on criteria such as source IP address, destination IP address, port number, and protocol type.

When a packet arrives at the firewall, the firewall checks its header fields against the rules in its access control list (ACL). If the packet matches one of the rules in the ACL, the firewall takes action based on that rule. For example, if the rule specifies that packets from a certain IP address should be blocked, the firewall will drop any packets that match that IP address

{{< hint info >}}
Rules listed first take precedence.
{{< /hint >}}

### Example Rules

- `allow tcp 4.5.5.4:1025 -> 3.1.1.2:80`: Permit tcp traffic from 4.5.5.4:1025 to 3.1.1.2:80

- `deny tcp 4.5.5.4:* -> 3.1.1.2:80`: Deny tcp traffic from ip 4.5.5.4 to 3.1.1.2:80

## Stateful Packet Inspection

Stateful packet inspection (SPI) is a firewall technique that examines the state of a connection as it passes through the firewall. This allows the firewall to make decisions about the traffic based on the state of the connection, rather than just the packet itself.

## Advantages

- Easy administration
- Central control - one config to change all security policies

## Disadvantages

- Functionality Loss - Firewalls limit the connections and thus may cause some application like peer-to-peer to not work.
- The deployment of a firewall assumes that the insiders are trusted. If an insider is compromised, the firewall can be bypassed.
- Firewalls are semantically limited and lack context of the data being transferred. This leaves them vulnerable to evasion techniques.

# Subverting Firewalls

There are a number of strategies a local user can employ to subvert or get around a local firewall.

## Abusing Ports

Packet filters have a fundamentally limited semantic model and lack a full understanding of the meaning of the traffic they carry. This means that they can be tricked into allowing traffic that they should be blocking.

One method of subversion is to abuse ports by using them for applications other than what they were intended for.

For example, port 53/udp is typically used for DNS traffic, but it could be used for other applications such as Skype or BitTorrent if the client and server agree on an application protocol.

A firewall can't block port 53 as it is used for DNS request and doing so will break the internet.

## Tunneling

Tunneling is a technique of embedding one protocol inside another. It involves encapsulating the data of one network protocol within the data packets of another protocol.

Firewall will only cater to the rules defined for the outer protocol.

VPNs are an example of tunneling.

# Application Proxy

An application proxy is a type of firewall that can more directly control applications by requiring them to go through a proxy for external access.

Unlike traditional firewalls, which simply forward traffic, an application proxy acts as an application-level middleman. For example, an SSH gateway can require all SSH in/out of site to go through the gateway, which logs authentication and inspects decrypted text. The site’s firewall can be configured to prohibit any other SSH access.

Application proxies provide a powerful degree of monitoring/control but require running extra server(s) per app (possible bottleneck) and each server requires careful hardening.
