---
weight: 25
title: "Denial of Service"
---

# Denial of Service

Denial of service (DoS) is a type of cyber attack that aims to make a website, network, or computer system unavailable to its intended users. I

## Approaches to DOS

### Via Program Flaw

Exploit the system via inputs or some other interaction such that the system crashes, becomes unresponsive or shuts down.

This can be avoided by:

- Careful coding/testing/review
- Careful authentication

### Via Resource Exhaustion

Exploit the system such that the the CPU, memory, disk or networks becomes overwhelmed and the system becomes unresponsive.

This can be avoided by:

- Isolation mechanisms
- Reliable identification schemes

# DOS as a Network Attack

A Network Denial of Service Attacks is when an attacker floods the target network or system with a large volume of traffic or requests, overwhelming its capacity to process and respond to these requests.

## DNS Amplification

{{< youtube xTKjHWkDwP0 >}}

## Filtering - Defense Mechanism

A network filter can be used to discard any packets arriving from a malicious ip.

Note that for this to work we need to know the ip of the attacker.

### Subverting Filtering

- **IP Spoofing**: Spoof the source IP address for the sent packets to a random address.
- **DDoS**: Use many hosts to send traffic to the target.

## DDoS Attacks

DDoS stands for Distributed Denial of Service. It is a type of cyberattack in which a large number of computers or devices (often called a botnet) are used to flood a target website or online service with an overwhelming amount of traffic or requests. The goal of a DDoS attack is to disrupt or completely disable the targeted website or service, making it inaccessible to legitimate users.

## Defense Mechanisms

### DDoS mitigation services

These are specialized services that can detect and filter out malicious traffic before it reaches the target website or service. They use a variety of techniques, such as rate limiting, traffic shaping, and IP blocking, to identify and block suspicious traffic.

### Cloud-based protection

Cloud-based DDoS protection services can help to provide scalable protection against DDoS attacks by using a network of servers to absorb and filter incoming traffic.

### Load balancers

Load balancers can distribute incoming traffic across multiple servers or data centers, which can help to prevent any one server from becoming overwhelmed.

### Content Delivery Network (CDN)

CDNs can help to distribute the load of incoming traffic across multiple servers and data centers, which can make it more difficult for attackers to overwhelm any one server. This can also help to improve the performance and availability of the website or service.
