---
weight: 35
title: "Transposition Ciphers"
---

# Transposition Ciphers

A transposition cipher is a method of encryption that involves rearranging the order of the characters in a message without changing the actual characters themselves

An example key of transposition cipher is:

{{< katex display >}} \begin{bmatrix} 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 1 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} {{< /katex >}}

Multiplying this key matrix with our plaintext vector will result in a cipher where the letters of plaintext are jumbled up:

{{< katex display >}} (1, 2, 3 ,4) \rightarrow (3, 1, 2, 4) {{< /katex >}}
