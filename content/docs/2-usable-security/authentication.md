---
weight: 30
title: "Authentication"
---

# Authentication

## Means of Authentication

1. Something a user knows

   - passwords
   - PIN
   - Patterns

2. Something a user has

    - Physical Keys
    - Smart cards

3. Something a user is

   - Fingerprint
   - Retina
   - Face recognition

4. Something a user does

   - Voice recognition
   - Handwriting recognition

## Passwords

Passwords are a knowledge based authentication mechanism.

### Strengths

- cheap to implement
- easy to renew and to revoke
- easy to understand & accessible
- users have been trained to use them
- hardware independent

### Weaknesses

- strong passwords are hard to remember
- dictionary attacks
- passwords are often predictable
- users do not know what a hard to crack password is
- theoretic password space vs. actually used password space
- password reuse/management
- fallback security questions

## Biometrics

### Strengths

- not as secure as marketed
- non-revocable
- doesn’t work 100% of the time
- requires fallback authentication
- accessibility problems (e.g. weak fingerprints due to intense manual labor)

### Weaknesses

- convenient
- effortless
- fast

## Behavioral Biometrics

Behavioral Biometrics are behavior based authentication mechanisms.

### Strengths

- implicit
- enables continuous authentication

### Weaknesses

- very weak measure
- many false positives/negatives
- does not work well under realistic conditions
- requires training
- requires data collection over a period of time for classification

# Other Authentication Methods

## Two Factor Authentication

Two factor authentication (2FA) is a method of confirming a user’s claimed identity by using two different components.

Its a combination of what users know and what they have.

{{< hint danger >}}
2FA is not very useable.
{{< /hint >}}

## Password Managers

Password managers are a way to store and manage passwords.

They solve the problem of:

- remembering passwords
- password reuse
- creation of strong passwords

{{< hint danger >}}
Password managers introduce a single point of failure.
{{< /hint >}}

## Fallback Authentication

Fallback authentication is a method of authentication that is used when the primary authentication method fails. These are often in form of security questions and PIN codes.

Studies have shown that users often choose even more weaker passwords when they are only used as fallback authentication. This makes all passwordless methods vulnerable to attacks.

{{< hint info >}}
Passwords can't be replaced because all alternative methods require a fallback authentication mechanism.
{{< /hint >}}

## Hardware Keys

Hardware keys are a way to authenticate a user by using a physical device.

Hardware keys are often in form of UBS sticks, smart cards or QR codes. The user needs to be in physical possession of the device to authenticate. Furthermore authenticity checks are needed to ensure that tokens and certificates are not replaced, modified, or counterfeit.

{{< hint danger >}}
Hardware keys are susceptible to Supply Chain Attacks.
{{< /hint >}}

# Evaluating Authentication Schemes

## Usability

- Memorywise-Effortless
- Scalable-for-Users
- Nothing-to-Carry
- Physically-Effortless
- Easy-to-Learn
- Efficient-to-Use
- Infrequent-Errors
- Easy-Recovery-from-Loss

## Dependability

- Accessible
- Negligible-Cost-per-User
- Server-Compatible
- Mature
- Non-Proprietary

## Security

- Resilient-to-Physical-Observation
- Resilient-to-Targeted-Impersonation
- Resilient-to-Throttled-Guessing
- Resilient-to-Unthrottled-Guessing
- Resilient-to-Internal-Observation
- Resilient-to-Leaks-from-Other-Verifiers
- Resilient-to-Phishing
- Resilient-toTheft
- No-Trusted-Third-Party
- Requiring-Explicit-Consent
- Unlinkable
