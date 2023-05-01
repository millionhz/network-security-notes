---
weight: 20
title: "Key Exchange Protocols"
---

# Key Exchange Protocols

Key Exchange Protocols are used to exchange the shared secret key of a symmetric & asymmetric encryption scheme over an insecure channel.

# Diffie Hellman Key Exchange

Used for symmetric encryption schemes.

## Theory

{{< youtube NmM9HA2MQGI >}}

## Mathematics

{{< youtube Yjrfm_oRO0w >}}

## Security

The security of Diffie-Hellman relies on the fact that given a large prime p, a generator g, and the values of g^a mod p and g^b mod p, it is computationally difficult to calculate the value of S = g^(ab) mod p.

This is known as the discrete logarithm problem, and no efficient algorithm is currently known to solve it for large prime numbers.

# Public Key Encryption Key Exchange (PKEKE)

Mainly used for asymmetric encryption schemes but can be used to share the key for symmetric encryption.

## Theory

Public key cryptography involves a key pair.

A public key is only used to encrypt the message and only the corresponding private key is used to decrypt the message.

The symmetric key is encrypted using the recipients public key and transmitted over the insecure channel. On the other end, the recipient uses their private key to decrypt the symmetric key. Now the shared symmetric key can be used to encrypt the communication.

# Key Exchange Vulnerabilities

Key Exchange protocols only protect against eavesdropping attacks.

Key Exchange protocols are not secure against **Man-in-the-Middle attacks**. Messages can be intercepted and tampered with by an adversary during key exchange.

{{< youtube vsXMMT2CqqE >}}

{{< hint info >}}

RSA Encryption solves this problem.

{{< /hint >}}
