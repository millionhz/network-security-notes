---
weight: 50
title: "DNS Cache Poisoning"
---

# DNS

The Domain Name System (DNS) is a protocol that translates human-readable domain names into IP addresses that are used to locate servers on the internet.

The DNS protocol uses the User Datagram Protocol (UDP) as the underlying transport layer protocol.

## DNS Packet

![](/images/20230220145125.png)

DNS packets are composed of several fields, including the header and the data sections. The important headers used in a DNS packet include:

1. ***Identification***: a 16-bit identifier that is used to match the request with the response.

2. **Flags**: a 16-bit field that contains several flags that control the behavior of the DNS query or response.

3. **Questions**: a 16-bit field that specifies the number of questions in the DNS query.

4. **Answers**: a 16-bit field that specifies the number of answers in the DNS response.

5. **Authority records**: a 16-bit field that specifies the number of authority records in the DNS response.

6. **Additional records**: a 16-bit field that specifies the number of additional records in the DNS response.

7. **Query section**: a section that contains the actual DNS query, including the domain name and the query type.

8. **Answer section**: a section that contains the IP address associated with the domain name in the DNS response.

9. **Authority section**: a section that contains information about the authoritative DNS server for the domain name in the DNS response.

10. **Additional section**: a section that contains additional information, such as the time-to-live (TTL) value for the DNS response.

## DNS Response

![](/images/dns-response.png)

1. `QUESTION SECTION`: Contains a copy of the original query that was sent by the DNS client in the corresponding DNS request.

2. `ANSWER SECTION`: Contains the response to the DNS query. The response contains DNS name, time-to-live, family, type (A here,
which stands for “Address”), and an associated value (IP address).

3. `AUTHORITY SECTION`: Contains information about the server responsible for the answer. The client will cache this and if the "Answer" had been empty, then the resolver’s next step would be to send the original query to one of these name servers.

4. `ADDITIONAL SECTION`: Provides extra information to save us from making separate lookups for it. For example, the DNS server may respond with the IP addresses for other servers that are associated with the domain. This additional information can be used by the client to optimize its future DNS queries or to establish connections to other services provided by the domain.

# DNS Cache Poisoning

DNS cache poisoning is a type of **DNS Spoofing** attack in which an attacker corrupts the DNS cache of a targeted computer or network, replacing legitimate domain name information with fraudulent or malicious data.

{{< youtube 7MT1F0O3_Yw >}}

## Poisoning `ADDITIONAL SECTION`

The attacker sends a DNS response to a resolver that includes a false IP address in the "additional" section of the response. The resolver, not realizing that the IP address is false, stores it in its cache along with the real IP address for the requested domain. When a user tries to access the domain later, the resolver may return the false IP address from its cache instead of the real IP address, redirecting the user to the attacker's fraudulent website.

### Prevention

We can prevent this attack by not accept `ADDITIONAL SECTION` unless they're from the domain of the hostname we queried.

For example, if contact a name server for mit.edu, only the "additional records" from *.mit.edu will get cached.

This is called **"bailiwick checking"**.

## Blind Spoofing

If the attacker knows that we are making a DNS Request, it just needs to **guess the identification field** and reply before the real DNS Server.

If the identification number is incremented by 1 on each request, the attacker can observe previous requests to guess the identification number of the next request.

### Prevention

We can randomize the identification number to prevent this attack. The attacker won't have enough time to guess the identification number and once the response arrives with the correct identification number, the response will be cached and further attempts by the attacker won't work.

## Kaminsky DNS Attack

The Kaminsky attacks work by preventing the client from caching the legit response. It does this by generation a series of different name lookups.

For example, make the victim make multiple requests to hostnames like `www.rand1.google.com` and `www.rand2.google.com` and so on. This will give the attacker plenty of time to guess the identification number.

### Prevention

For an DNS response to be accepted, the response must have the correct identification number but also the correct source and destination port numbers.

We can increase the entropy of the systems by **randomizing the port numbers** thus making it harder for the attacker to guess the correct value of the fields.
