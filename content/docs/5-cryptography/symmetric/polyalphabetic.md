---
weight: 30
title: "Polyalphabetic Cipher"
---

# Polyalphabetic Cipher

Instead of mapping each character to a single character, map 2 characters to 2 characters (digram mapping).

## Key Space

Because now characters are mapped to 2 characters, we have 26^2 pairings for one set of characters, leaving us with a total of (26^2)! possible keys.

{{< hint info >}}
The key here will be 26*2 characters long. Long Keys are problematic.
{{< /hint >}}

## Frequency Attack

Polyalphabetic ciphers are still prone to frequency attacks. This is because the frequency of digrams in the Cipher will match the frequency of digrams in the English language.

This problem can be mitigated by using longer digrams.

# Vigenere Cipher

Use a key of fixed size to encrypt the whole text. If the key is shorter than the plain text, repeat the key.

{{< katex display >}} C_i = (p_i + k_{i \ mod \ m}) \ mod \ 26 {{< /katex >}}

{{< katex display >}} p_i = (C_i - k_{i \ mod \ m}) \ mod \ 26 {{< /katex >}}

![](/images/20230403035342.png)

{{< hint info >}}
Vigenere Cipher solves the problem of long keys by using a key that is of a fixed size.
{{< /hint >}}

## Vulnerability

Repeating plain text encrypted with the repeating key of the Vigener Cipher will result in the same cipher text. An attacker can use this info to extract information about the key.

This is due to the fact that the key length is shorter than the cipher length.

# Vernam / One-time Pad ⭐

Key length is equal to the message length.

XOR each bit of the plain text with each bit of the key.

{{< katex display >}} C_i = p_i \oplus k_i {{< /katex >}}

{{< katex display >}} p_i = C_i \oplus k_i {{< /katex >}}

| Symbol | Description |
|--------|-------------|
|  {{< katex >}} p_i {{< /katex >}} | ith but of the plain text  |
|  {{< katex >}} k_i {{< /katex >}} | ith but of the key  |
|  {{< katex >}} C_i {{< /katex >}} | ith but of the cipher  |

## One-Time Pad

- The key is used only once.
- The key is selected at random.

**Abiding by these 2 rules makes the cipher unbreakable.**

A certain cipher text with different keys can map to different plain texts.

The attacker will not be able to figure out the key that outputs the correct plain text.

## Problems - Impractical

- Key Generation
- Key Distribution

Both of these problems stem from the fact that the key length is equal to the message length.

# Hill Cipher

The key of hill cipher is a square invertible matrix.

For encryption, the plain text is split into blocks (vectors) of size equal to the size of the key matrix. Each block is multiplied with the key matrix to get the cipher text.

{{< katex display >}} C = PK \ mod \ 26 {{< /katex >}}

For decryption, the cipher text is split into blocks (vectors) of size equal to the size of the key matrix. Each block is multiplied with the inverse of the key matrix to get the plain text.

{{< katex display >}} P = PK^{-1} \ mod \ 26 {{< /katex >}}

{{< youtube 6T46sgty4Mk >}}
