---
weight: 10
title: "RSA"
---

# RSA

RSA is a public-key cryptosystem used for secure data transmission over the internet.

## Key Generation

### Prime Numbers

Generate two large prime numbers {{< katex >}} p {{< /katex >}} and {{< katex >}} q {{< /katex >}}.

### Calculate n and totient of n

{{< katex display >}} n = p * q {{< /katex >}}

{{< katex display >}} \phi(n) = (p-1)(q-1) {{< /katex >}}

### Calculate e

{{< katex >}} e {{< /katex >}} is a number relatively prime to {{< katex >}} \phi(n) {{< /katex >}}.

{{< katex display >}} e \in \mathbb{Z}^{+} {{< /katex >}}

{{< katex display >}} e < \phi(n) {{< /katex >}}

{{< katex display >}} gcd(e, \phi(n)) = 1 {{< /katex >}}

### Calculate d

{{< katex >}} d {{< /katex >}} is the modular inverse of {{< katex >}} e {{< /katex >}} mod {{< katex >}} \phi(n) {{< /katex >}}.

{{< katex display >}} d \in \mathbb{Z}^{+} {{< /katex >}}

{{< katex display >}} d*e \ mod \ \phi(n) = 1 {{< /katex >}}

### Generate Key Paior

{{< katex >}} (e,n) {{< /katex >}} is the public key.

{{< katex >}} (d,n) {{< /katex >}} is the private key.

## Encryption

{{< katex display >}} C = M^{e} \ mod \ n {{< /katex >}}

## Decryption

{{< katex display >}} M = C^{d} \ mod \ n {{< /katex >}}
