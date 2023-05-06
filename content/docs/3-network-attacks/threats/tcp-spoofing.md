---
weight: 40
title: "TCP Spoofing"
---

# TCP Spoofing

TCP spoofing, also knows as Session Hijacking,  is a type of cyber attack in which an attacker impersonates another computer or device on a network in order to intercept and **manipulate** the data being sent between the two devices.

On-Path attackers can see the traffic between two hosts and can spoof the traffic to impersonate one of the hosts.

Off-Path attackers (blind spoofing) may need to infer headers and brute force sequence numbers to spoof traffic.

## Blind TCP Spoofing

A TCP spoof attack can be carried out with just the valid **port** and **sequence number** without needing the complete TCP traffic.

## TCP Spoofing Workflow

1. **Craft the packet**: The attacker needs to craft the packet so that it appears to be a legitimate packet. This includes setting the appropriate flags, including the correct sequence number and acknowledgment number, and setting the payload if necessary.

2. **Send the packet**: Once the packet has been crafted, the attacker sends it to the target system. The system will receive the packet and send a response back to the source IP address

3. **Analyze the response**: The attacker now needs to analyze the response from the target system to determine if the spoofed packet was successful. If the response indicates that the packet was successful, the attacker can continue with the attack.

## Sequence Number & Blind Spoofing

When the connection establishes both hosts pick a Initial Sequence Number based on a clock and share it with each other. An attacker can listen on their traffic and figure out the ISN.

With the ISN the attacker can calculate the sequence number of the next packet or the nth packer.
