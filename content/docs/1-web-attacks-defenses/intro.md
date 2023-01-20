---
weight: 10
title: "Introduction"
---

# Client Server Architecture

The internet uses a client-server architecture, where the browser is the client and the web server is the server. The client sends a request to the server, which then responds with the requested resource.


# Browser Threats

## Compromise

**Inject Code**:
Injecting code refers to the process of inserting malicious code into a legitimate program or website.

**Malware**:
Installing malware refers to the act of installing harmful software on a victim's device, which can be used to gain access to sensitive information or take control of the device.

## Theft

**Data Theft**:
Data theft refers to the unauthorized access and exfiltration of sensitive information, such as credit card numbers or personal data.

**Session Hijacking**:
Session hijacking refers to the act of taking over an active session, such as a logged-in account, by intercepting and using session cookies or other information.

## Manipulation

**Phishing**:
Phishing refers to the use of social engineering tactics, such as email or social media, to trick individuals into revealing sensitive information or visiting a malicious website.

**Spoofing**:
Spoofing refers to the act of disguising oneself as another entity, such as an email sender or website, to gain access to sensitive information or resources.

# HTTP

## URLs

```
http://coolsite.com/tools/doit.php?cmd=play&vol=44
```


| Components | Description     |
| ---------- | --------------- |
| Protocol   | http            |
| Host       | coolsite.com    |
| Path       | /tools/doit.php |
| Arguments  | cmd=play&vol=44 |


## HTTP Request

![](/images/20230119142359.png)

## HTTP Response

![](/images/20230119144325.png)

## Headers

[HTTP Headers - MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)

## Cookies

[HTTP Cookies - MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)

Cookies are used to hold state information. They are set by the server and are sent back to the server with every request. Cookies usually include session identifiers and authentication information.

However, cookies are susceptible to theft. A hacker can steal a user's cookies from their device and use them to impersonate the user and gain unauthorized access to their account. This is why it is important to protect your device and use a secure network when using cookies.

# Same-Origin Policy

The Same-Origin Policy (SOP)  controls the abilities of web pages to interact with resources from different origins (domains, protocols, and ports).

Specifically, the SOP only allows web pages to access resources from the same origin (defined as having the same combination of domain, protocol, and port. This means that a web page loaded from "https://example.com" can only access resources (such as cookies, local storage, and APIs) from the same origin.

It prevents cross-site scripting (XSS) and cross-site request forgery (CSRF) attacks by limiting the ability of a malicious web page to access resources from a different site, using the user's credentials or cookies.

*Web technologies such as CORS (Cross-Origin Resource Sharing) allow web pages to access resources from different origins, under certain conditions.*