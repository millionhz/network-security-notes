---
weight: 70
title: "DNSSEC"
---

# DNSSEC

DNSSEC (Domain Name System Security Extensions) is a standardized set of security extensions for the Domain Name System (DNS).

## Procedu re

When a resolver works its way from the DNS root down to the final name server for a name, at each level, it receives a signed statement regarding the key(s) used by the next level. This means that DNSSEC builds up a chain of trusted keys, where each level is authenticated by the level above it.

The resolver has the root's key wired into it, which means that it trusts the root key without any additional authentication. The final answer that the resolver receives is signed by that level's key, which the resolver can trust because of the chain of support from higher levels.

All keys as well as signed results are cacheable, which means that once a resolver has received and authenticated a signed response, it can store the information in its cache for future reference. This reduces the need for repeated authentication requests and speeds up the overall process.

## Why can't we use DNS over TLS?

- DNS needs to be lightweight and fast but TLS is not.
- DNS makes use of caching for scaling which will not be possible with TLS.

## Issues

1. DNSSEC responses are huge:
   - Ths provides adversaries with an opportunity of DoS amplification.
   - Increases latency over low-capacity links

2. Partial deployment:
   - DNSSEC is not deployed everywhere. This means that the resolver will not be able to verify the authenticity of the DNS response.

3. Key Management:
   - DNSSEC requires the management of keys. This is a complex task and requires a lot of resources.

4. Can not sign domains that do not exist.

5. DNSSEC does not provide confidentiality.
