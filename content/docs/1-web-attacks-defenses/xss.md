---
weight: 30
title: "Cross-Site Scripting (XSS)"
---

# Cross-site Scripting (XSS)

An XSS (Cross-Site Scripting) attack is a type of injection attack in which an attacker injects malicious code, usually in the form of a script, into a web page viewed by other users.

When the other users load the web page, the malicious script is executed by their web browser, allowing the attacker's code to run and steal sensitive information such as cookies, session tokens, and other personal data.

{{< youtube EoaDgUgS6QA >}}


## Stored XSS

The attacker injects a malicious script into a web page, which is then stored on the server and served to all users who view the page.


## Reflected XSS

The attacker injects a malicious script into a web page by sending a specially **crafted link** to a victim, which includes the script as part of the link. When the victim clicks on the link, the script is executed by their web browser.


## XSS Workflow

1. The attacker crafts a malicious script, usually in form of JavaScript, and injects it into a web page. *This can be done by exploiting a vulnerability in the website's code or by tricking the website's administrator into adding the script.*
2. (The victim then visits the compromised website, either by getting tricked by the attacker on by their own accord)
3. The victim's browser loads the web page and executes the malicious script. This can happen automatically when the page is loaded, or when the victim clicks on a link or button on the page.
4. The malicious script can then steal sensitive information such as cookies, session tokens, and personal data from the victim's browser and send it back to the attacker.

## Defenses against XSS


**Input validation** - *whitelisting*:
Sanitize all user input, headers, cookies, query strings and form fields against a rigorous specification of allowed characters.

**Output encoding** - *blacklisting*:
Encode all output that is based on user input, so that any special characters (script tags) are rendered harmless.

**Regular security testing**:
Regularly test your website for XSS vulnerabilities using tools like OWASP ZAP or Burp Suite.
