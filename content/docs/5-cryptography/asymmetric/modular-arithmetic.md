---
weight: 5
title: "Modular Arithmetic"
---

# Modular Arithmetic

{{< youtube Y68It2Hvowo >}}

## Identities

### Modular Inverse

{{< katex >}} b {{< /katex >}} is inverse of {{< katex >}} a {{< /katex >}} if:

{{< katex display >}} a*b \ mod \  n = 1 {{< /katex >}}

Find {{< katex >}} b {{< /katex >}}  using the Euclidean Algorithm.

### Relatively Prime

{{< katex >}} a {{< /katex >}} and {{< katex >}} b {{< /katex >}} are relatively prime if:

{{< katex display >}} gcd(a,b) = 1 {{< /katex >}}

### Totient

Let

{{< katex display >}} Z_n^{*} = \{ \text{relatively prime numbers to n } \} {{< /katex >}}

Totient of n:

{{< katex display >}} \phi(n) = |Z_n^{*}| {{< /katex >}}

Also, if:

{{< katex display >}} n = p * q {{< /katex >}}

where {{< katex >}} p {{< /katex >}} and {{< katex >}} q {{< /katex >}} are prime, then:

{{< katex display >}} \phi(n) = (p-1)(q-1) {{< /katex >}}

### Euler's Theorem

{{< katex display >}} x^k \ mod \ n = x^{k \ mod \ \phi(n) } \ mod \ n {{< /katex >}}
