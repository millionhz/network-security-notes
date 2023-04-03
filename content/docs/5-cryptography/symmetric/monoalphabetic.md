---
weight: 20
title: "Monoalphabetic Cipher"
---

# Caesar Cipher

Ceaser Substitute the plaintext with a different character.

{{< katex display >}} C = E(k, p) = (p + k) \ mod \ 26 {{< /katex >}}
{{< katex display >}} p = D(k, C) = (C - k) \ mod \ 26 {{< /katex >}}

## Key space

For Caesar cipher, the key space is just a number.

There are only 25 possible keys because there are only 25 ways to shift the alphabets.

## Brute Force

The small key space leaves caesar ciphers vulnerable to **brute-force attacks**. The attacker just needs to try all (only) 25 keys to get the plaintext.

# Generalized Monoalphabetic Cipher

Instead of shifting characters by one, make random pairings to improve key space. E.g. pair `a` with `d`, `b` with `e`, `c` with `f`, etc.

## Key space

Here key is the way we can arrange the 26 alphabets.

There are 26 characters in the alphabet, so there are 26! possible keys.

## Frequency Attack

The frequencies of characters used in the cipher text will match up with the frequencies of characters in the English language. We can use this semantic knowledge to guess the plaintext.
