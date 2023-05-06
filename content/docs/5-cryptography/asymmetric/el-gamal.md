---
weight: 20
title: "El Gamal"
---

# El Gamal Cryptosystem

El Gamal is a public key cryptosystem that behaves like Diffie Hellman but also allows us to encrypt and decrypt messages.

Furthermore unlike Diffie Hellman, both parties do not need to participate for El Gamal to work.

{{< youtube qZsWk9i3EDQ >}}

## Procedure

The sender only has access to the receivers Public Key. in form:

{{< katex display >}} B = g^{b} \ mod \ p {{< /katex >}}

### Encryption

Generate a random number r.

{{< katex display >}} r \in \mathbb{Z}^{+} {{< /katex >}}

Compute key R.

{{< katex display >}} R = g^{r} \ mod \ p {{< /katex >}}

Encrypt the message with the random number r and key B.

{{< katex display >}} C = M \times B^{r} \ mod \ p {{< /katex >}}

Transmit the encrypted message C and key R.

### Decryption

{{< katex display >}} M = R^{-b} \times C {{< /katex >}}
