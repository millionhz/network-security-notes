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

## Defense Mechanisms
