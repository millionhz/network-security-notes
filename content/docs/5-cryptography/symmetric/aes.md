---
weight: 40
title: "AES"
---

# Advanced Encryption Standard (AES) - SP Network Cipher

{{< youtube UF4Bdx0QQxI >}}

AES is a symmetric block cipher. It uses a 128-bit (16 bytes) block size and a 128, 192, or 256-bit key size to encrypt the block of plain text.

AES utilizes both Substitution and Transposition.

| Key Size | Rounds |
|----------|--------|
| 128-bit  | 10     |
| 192-bit  | 12     |
| 256-bit  | 14     |

## Encryption

### Key Expansion

Generate keys for each round from the original key. Number of keys generated is equal to the number of rounds + 1.

### Initial Round

Add the first round key to the plain text to create the cipher text.

### Rounds

Repeat the following steps for the number of rounds - 1.

1. Substitute Bytes: Substitute each byte of the state matrix with a different byte from the S-Box. S-Box is predefined and is used to substitute the bytes.

2. Shift Rows: Shift the rows of the state matrix by different offsets. Row 0 is shifted by 0 bytes, Row 1 is shifted by 1 byte, Row 2 is shifted by 2 bytes and so on.

3. Mix Columns: Mix the columns of the state matrix by multiplying the state with a fixed matrix.

4. Add Round Key: Combines the state matrix with the current round key through bitwise XOR operation.

## Key Space

The key space depends on the size of the key.

{{< katex display >}} Key \ Space = 2^{key \ size} {{< /katex >}}

## Attacks

- Exhaustive Key Search
- Side Channel Attack

## Also See

{{< youtube O4xNJsjtN6E >}}

# Encryption Modes

{{< youtube Rk0NIQfEXBA >}}

## Electronic Code Block (ECB) Mode

Each Block is encrypted independently.

### Pros

- Simplicity
- Tolerate Losses - a corrupted block will not affect other blocks as every block is encrypted independently

### Cons

- Same plaintext is encrypted to the same ciphertext and can thus reveal patterns in the plaintext. (ECB Penguin)

## Cipher Block Chaining (CBC) Mode

Use previous cipher to calculate the cipher for the current block. When encrypting the first block use an initialization vector (IV) as the previous cipher.

{{< katex display >}} C_0 : Initialization \ Vector {{< /katex >}}

{{< katex display >}} C_i = E_k(B_i \oplus C_{i-1}) {{< /katex >}}

{{< katex display >}} B_i = D_k(C_i \oplus C_{i-1}) {{< /katex >}}

### Pros

- Fixes ECB Penguin
- Tolerate losses - if a block is lost, at the maximum two block will be affected (the lost block and the next block)

### Cons

- Encryption happens sequentially, not parallelizable.

## Cipher Feedback (CFB) Mode

Encrypt the last block and XOR it with the current block.

{{< katex display >}} C_i = E_k(C_{i-1}) \oplus B_i {{< /katex >}}

{{< katex display >}} B_i = D_k(C_{i-1}) \oplus C_i {{< /katex >}}

### Pros

- Faster - Decryption is not applied to the whole block, only the last block.

## Output Feedback (OFB) Mode

OFB follows the principle of one-time pad by using the provided key and the initialization vector (IV) to generate a stream of bits(expanded). The stream is then XORed with the plaintext to produce the ciphertext.

{{< katex display >}} V_0 : Initialization \ Vector {{< /katex >}}

{{< katex display >}} V_i = E_k(V_{i-1}) {{< /katex >}}

{{< katex display >}} C_i = B_i \oplus V_i {{< /katex >}}

{{< katex display >}} B_i = C_i \oplus V_i {{< /katex >}}

### Pros

- Parallelizable - After the Key Blocks (keys stream from initialization vector) is generated, the XOR operation on the blocks can be applied in parallel.
- Tolerate losses - Each block is encrypted independently.

## Counter (CTR) Mode

Use a **random seed** and counter to generate a stream of bits(expanded).

{{< katex display >}} S : Random \ Seed {{< /katex >}}

{{< katex display >}} i : Counter {{< /katex >}}

{{< katex display >}} V_i = E_k(S + i - 1) {{< /katex >}}

{{< katex display >}} C_i = B_i \oplus V_i {{< /katex >}}

{{< katex display >}} B_i = C_i \oplus V_i {{< /katex >}}

### Pros

- Completely parallelizable
- Tolerate Losses
