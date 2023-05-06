---
weight: 25
title: "Denial of Service"
---

# Denial of Service

Denial of service (DoS) is a type of cyber attack that aims to make a website, network, or computer system unavailable to its intended users.

## Approaches to DOS

### Via Program Flaw

Exploit the system via inputs or some other interaction such that the system crashes, becomes unresponsive or shuts down.

This can be avoided by:

- Careful coding/testing/review
- Careful authentication

### Via Resource Exhaustion

Exploit the system such that the the CPU, memory, disk or networks becomes overwhelmed and the system becomes unresponsive.

This can be avoided by:

- Isolation mechanisms: Keep adversary’s consumption from affecting others
- Reliable identification schemes

# DOS as a Network Attack

A Network Denial of Service Attacks is when an attacker floods the target network or system with a large volume of traffic or requests, overwhelming its capacity to process and respond to these requests.

For a DoS attack of be successful an adversary needs to send enough packets to overwhelm the target's:

- bottleneck link
- bottleneck router

## DNS Amplification

{{< youtube xTKjHWkDwP0 >}}

## Filtering - Defense Mechanism

A network filter can be used to discard any packets arriving from a malicious ip.

Note that for this to work we need to know the ip of the attacker.

### Subverting Filtering

- **IP Spoofing**: Spoof the source IP address for the sent packets to a random address.
- **DDoS**: Use many hosts to send traffic to the target.

## DDoS Attacks

[What is DDoS - cloudflare](https://www.cloudflare.com/learning/ddos/what-is-a-ddos-attack/)

DDoS stands for Distributed Denial of Service. It is a type of cyberattack in which a large number of computers or devices (often called a botnet) are used to flood a target website or online service with an overwhelming amount of traffic or requests. The goal of a DDoS attack is to disrupt or completely disable the targeted website or service, making it inaccessible to legitimate users.

## Defense Mechanisms

### Blackhole routing

One solution available to virtually all network admins is to create a blackhole route and funnel traffic into that route. If an Internet property is experiencing a DDoS attack, the property’s Internet service provider (ISP) may send all the site’s traffic into a blackhole as a defense.

### Anycast network diffusion

This mitigation approach uses an Anycast network to scatter the attack traffic across a network of distributed servers to the point where the traffic is absorbed by the network.

### DDoS mitigation services

These are specialized services that can detect and filter out malicious traffic before it reaches the target website or service. They use a variety of techniques, such as rate limiting, traffic shaping, and IP blocking, to identify and block suspicious traffic.
