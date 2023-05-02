---
weight: 20
title: "Cryptographic Hashes"
---

# Cryptographic Hash Function

Hash functions are **deterministic** and **unkeyed** functions that take an arbitrary length input and produce a fixed length output.

Even though hash functions are unkeyed they can still be used to **ensure integrity** if the hash is communicated over a **secure** channel.

## Properties

- **One-way/Pre-image Resistant**: Given a hash value, it is computationally infeasible to find a message that hashes to that value.

- **Second Pre-image Resistant**: Given a message, it is computationally infeasible to find **another message** that hashes to the same value.

- **Collision Resistant**: It is computationally infeasible to find **any two messages** that hash to the same value.

# Generic Birthday Attacks

A birthday attack is a cryptographic attack that takes advantage of the fact that in a large enough group of people (or items), it is highly likely that two people (or items) will have the same birthday. In the same way, in cryptography, it is possible to exploit the fact that different inputs can produce the same output (called a collision) in certain hash functions.

A generic birthday attack is an attack where the attacker tries to find two different inputs that produce the same hash output. To do this, the attacker generates a large number of random inputs and computes their hash values until they find two inputs that hash to the same output

## Probability of a collision

The probability of a collision is given by the following formula:

{{< katex display >}} P(n) = 1 - e^{-\frac{n^2}{2m}} {{< /katex >}}

Where:

- {{< katex inline >}} n {{< /katex >}} is the number of inputs
- {{< katex inline >}} m {{< /katex >}} is the number of possible outputs

For example, let's say we have a hash function with a 128-bit output, and we want to know the probability of finding a collision after hashing {{< katex inline >}} 2^{64} {{< /katex >}} (approximately 18 quintillion) random inputs. Using the formula, we get:

{{< katex display >}} P(2^{64}) = 1 - e^{-\frac{(2^{64})^2}{2*2^{128}}} {{< /katex >}}

{{< katex display >}} P(2^{64}) = 1 - e^{-2^{64}} {{< /katex >}}

{{< katex display >}} P(2^{64}) = 0.50 {{< /katex >}}

This means that there is a 50% chance of finding a collision after hashing {{< katex inline >}} 2^{64} {{< /katex >}} random inputs with a 128-bit hash function.

# Common Hash Functions

| Name | Output Size |
| ---- | ----------- |
| MD5 | 128 bits |
| SHA-1 | 160 bits |
| SHA-256 |  256 bits|
| SHA-512 | 512 bits |
