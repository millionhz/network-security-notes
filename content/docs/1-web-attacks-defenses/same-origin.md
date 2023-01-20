---
weight: 20
title: "Same-Origin Policy"
bookFlatSection: false
---

# Same-Origin Policy

The Same-Origin Policy (SOP)  controls the abilities of web pages to interact with resources from different origins (domains, protocols, and ports).

Specifically, the SOP only allows web pages to access resources from the same origin (defined as having the same combination of domain, protocol, and port. This means that a web page loaded from "https://example.com" can only access resources (such as cookies, local storage, and APIs) from the same origin.

It prevents cross-site scripting (XSS) and cross-site request forgery (CSRF) attacks by limiting the ability of a malicious web page to access resources from a different site, using the user's credentials or cookies.

*Web technologies such as CORS (Cross-Origin Resource Sharing) allow web pages to access resources from different origins, under certain conditions.*
