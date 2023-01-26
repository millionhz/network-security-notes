---
weight: 10
title: "Clickjacking"
---

# Clickjacking

Clickjacking is a malicious technique used to trick a user into clicking on a button or link on a different website than the one they intended.

The attacker uses code to create a frame on the page that contains the button or link, and makes it appear as if it is part of the original website. When the user clicks the button or link, they are actually performing an action on the other website, without knowing it. (This sort of things are done by using `<iframe>` tags)

- [Clickjacking - hacksplaing](https://www.hacksplaining.com/exercises/click-jacking)

- [Constructing Clickjacking Attack - portswigger](https://portswigger.net/web-security/clickjacking)

## Defenses against clickjacking

### Frame Bursting & `X-Frame-Options`

Websites can ensure that their pages can not be loaded as frames in other websites by setting the `X-Frame-Options` header to `DENY`.

*This functionality is implemented in browser.*
