---
weight: 30
title: "TCP Spoofing"
---

# TCP Spoofing

TCP spoofing is a type of cyber attack in which an attacker impersonates another computer or device on a network in order to intercept and **manipulate** the data being sent between the two devices.

## Blind TCP Spoofing

Is it possible for an attacker to inject into a TCP connection even if they can’t see our traffic if they know the port and sequences numbers.

## TCP Spoofing Workflow

1. **Identify the target system**: The first step in blind TCP spoofing is to identify the target system. This can be done by scanning the network or by using other reconnaissance techniques.

2. **Identify an open port**: Once the target system has been identified, the attacker needs to identify an open port that can be used for the spoofed packets. Commonly used ports include TCP ports 80 (HTTP), 443 (HTTPS), and 22 (SSH).

3. **Spoof the source IP address**: The attacker now needs to create a spoofed packet with a source IP address that appears to be from a legitimate device or server.

4. **Craft the packet**: The attacker needs to craft the packet so that it appears to be a legitimate packet. This includes setting the appropriate flags, including the correct sequence number and acknowledgment number, and setting the payload if necessary.

5. **Send the packet**: Once the packet has been crafted, the attacker sends it to the target system. The system will receive the packet and send a response back to the source IP address

6. **Analyze the response**: The attacker now needs to analyze the response from the target system to determine if the spoofed packet was successful. If the response indicates that the packet was successful, the attacker can continue with the attack.

## Sequence Number & Blind Spoofing

When the connection establishes both hosts pick a Initial Sequence Number based on a clock and share it with each other. An attacker can listen on their traffic and figure out the ISN.

With the ISN the attacker can calculate the sequence number of the next packet or the nth packer.
