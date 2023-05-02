---
weight: 40
title: "Public Key Infrastructure"
---

# Public Key Infrastructure

Public Key Infrastructure solves the problem of man-in-the-middle attacks by providing a way to verify the authenticity of a public key.

It involves:

- Certificate Authority (CA): Trusted third party responsible for verifying identity of users and issuing certificates.
- Digital Certificate: Contains the public key and the owner's name.

## Procedure

1. Alice needs to obtain a certificate from a trusted party. This certificate contains her name and public key. The trusted party verifies Alice's identity before issuing the certificate.

2. Alice sends the entire certificate to Bob.

3. Bob verifies the certificate using the trusted party's public key. This ensures that the certificate is authentic and has not been tampered with.

4. Once Bob verifies the certificate, he knows that the public key belongs to the true owner, which is Alice in this case.

## Certificate Authorities

Certificate Authorities exist in a hierarchy. The root CA is the most trusted and is responsible for issuing certificates to intermediate CAs. The intermediate CAs are responsible for issuing certificates to end sub CAs and so on.

{{< hint info >}}

Root CAs self sign their own certificates.

{{< /hint >}}

## Types of Digital Certificates

### Domain Validated Certificates (DV)

These certificates are the most basic type of digital certificate and are used to verify the ownership of a domain.

The validation process for these certificates involves the certificate authority (CA) verifying that the applicant owns or has control over the domain by sending an email to the domain's WHOIS contact email address or by checking a DNS record.

### Organization Validated Certificates (OV)

hese certificates are more rigorous than DV certificates and require additional validation.

In addition to verifying domain ownership, the certificate authority also verifies the identity of the organization that owns the domain.

This validation process typically involves checking the organization's legal registration and physical address.

### Extended Validation Certificates (EV)

These certificates are the most comprehensive and rigorous type of digital certificate.

They require the highest level of validation, which includes verifying domain ownership, organization identity, and legal existence.

The validation process for EV certificates involves a thorough review of the organization's identity and legal documentation.

The result is that the address bar in web browsers turns green, and users can see the name of the organization that owns the website, which provides an additional layer of trust and security.

## Certificate Revocation

To improve the security of the system, the CA can revoke a certificate if it is compromised or if the owner's private key is compromised.

This can be done by adding the certificate to a Certificate Revocation List (CRL) or by using the Online Certificate Status Protocol (OCSP).
