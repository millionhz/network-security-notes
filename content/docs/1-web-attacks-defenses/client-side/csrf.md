---
weight: 10
title: "Cross-Site Request Forgery (CSRF)"
---

# Cross-Site Request Forgery (CSRF) attack

A CSRF (Cross-Site Request Forgery) attack occurs when a malicious website or attacker tricks a victim's browser into making a request to a different website that the victim is already authenticated to.

{{< youtube eWEgUcHPle0 >}}

## CSRF Workflow

1. The attacker creates a website or webpage that contains a form or link that will make a request to a target website.
2. The attacker tricks the victim into visiting the malicious website or webpage, for example by sending the victim a link in an email or instant message.
3. The victim's browser makes the request to the target website, using the victim's authenticated session.
4. The target website performs the requested action, such as transferring money or changing the victim's account settings, without the victim's knowledge or consent.

## Defenses against CSRF

*CSRF Protection is primarily server side.*

### Referrer Checking

This involves checking the **referrer header** on a request to ensure that it originates from the same site as the one that set the cookie.

### SameSite Cookies

This is a cookie attribute that tells the browser to only send the cookie with requests sent to the same site as the one that set the cookie. This prevents the browser from sending the cookie with cross-site requests.

### Anti-CSRF tokens

A unique, unpredictable value is included with each request, and checked by the server to ensure that the request is legitimate.

### Two Factor Authentication

Require authentication (e.g. OTPs) for serious requests.
