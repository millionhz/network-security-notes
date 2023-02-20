---
weight: 40
title: "DNS Cache Poisoning"
---

# DNS

The Domain Name System (DNS) is a protocol that translates human-readable domain names into IP addresses that are used to locate servers on the internet.

The DNS protocol uses the User Datagram Protocol (UDP) as the underlying transport layer protocol.

## DNS Packet

![](/images/20230220145125.png)

DNS packets are composed of several fields, including the header and the data sections. The important headers used in a DNS packet include:

1. **Transaction ID**: a 16-bit identifier that is used to match the request with the response.

2. **Flags**: a 16-bit field that contains several flags that control the behavior of the DNS query or response.

3. **Questions**: a 16-bit field that specifies the number of questions in the DNS query.

4. **Answers**: a 16-bit field that specifies the number of answers in the DNS response.

5. **Authority records**: a 16-bit field that specifies the number of authority records in the DNS response.

6. **Additional records**: a 16-bit field that specifies the number of additional records in the DNS response.

7. **Query section**: a section that contains the actual DNS query, including the domain name and the query type.

8. **Answer section**: a section that contains the IP address associated with the domain name in the DNS response.

9. **Authority section**: a section that contains information about the authoritative DNS server for the domain name in the DNS response.

10. **Additional section**: a section that contains additional information, such as the time-to-live (TTL) value for the DNS response.

# DNS Cache Poisoning

DNS cache poisoning is a type of cyber attack in which an attacker corrupts the DNS cache of a targeted computer or network, replacing legitimate domain name information with fraudulent or malicious data.

{{< youtube 7MT1F0O3_Yw >}}

## Cache Poisoning Workflow

## Defense against Cache Poisoning
