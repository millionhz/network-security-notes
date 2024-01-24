---
weight: 30
title: "Digital Signatures"
---

# Digital (RSA) Signatures

Provides integrity and authenticity via **Asymmetric Key Cryptography**.

A digital signature is a way to verify the authenticity of an electronic document, email, or message.

## Procedure

The signer calculates the hash of the document which is then encrypted using the signers **private key** (document signature) and sent along with the document.

The verifier obtains the signed document, along with the signer's public key.

The verifier then computes the hash of the received document and the decrypt the document signature sent along using the signers public key. If both the calculated hash and decrypted hash match, the document was not tampered with and the signer is authentic.

{{< hint warning >}}

**RSA signatures do not provide non-mutability if the signature is applied on the *raw message* instead of the message hash**. This is due to the mathematical properties of modular arithmetics.

Non-mutability is only ensured if the signatures use hashes.

{{< /hint >}}
