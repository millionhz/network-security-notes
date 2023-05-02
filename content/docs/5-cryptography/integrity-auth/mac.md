---
weight: 10
title: "MACs"
---


# Message Authentication Codes

**Provides integrity not confidentiality.**

We want to make sure that the data was not tempered with during transmission.

## Procedure

The sender uses the message and a shared key to generate a MAC. The
{{< katex display >}} k : key {{< /katex >}}

{{< katex display >}} m : message {{< /katex >}}

{{< katex display >}} tag = S(k, m) {{< /katex >}}

Tag is then sent along with the message. The receiver uses the message, the shared key and the tag to verify the integrity of the message.

{{< katex display >}} V(k, m, tag) \stackrel{?}{=} yes {{< /katex >}}

{{< hint warning >}}

If a secret shared key is not used. An adversary can act as a man-in-the-middle and generate a new (message, tag) pair and the receiver will not be able to detect the tampering.

{{< /hint >}}

## MAC Security & Chosen Message Attack

The attacker in this scenario can choose messages to be authenticated and get access to the corresponding tags.

The attackers goal is to achieve existential forgery which means creating a new **valid** message and a tag pair that was not generated by the sender.

If the attacker can not achieve this in a reasonable amount of time, the MAC is considered secure.

If the tag space is small, the attacker will be able to exhaustively search the tag space and find a valid tag for a new message rendering the MAC insecure.

# CBC-MAC - Securing MAC using AES

The algorithm utilizes two keys to generate a tag.

Key 1 is used to encrypt the message using AES in CBC mode. This is called raw-CBC.

Key 2 is used with the output of the last block to create the tag.

{{< katex display >}} k_1 : key_1 {{< /katex >}}

{{< katex display >}} k_2 : key_2 {{< /katex >}}

{{< katex display >}} m : message {{< /katex >}}

{{< katex display >}} tag = AES_{k_2}(AES_{k_1}(m)) {{< /katex >}}

## Why do we need 2 keys?

CBC-MAC with only one key can be broken by a chosen message attack.

An attacker who knows the message and its authentication tag can manipulate the last block of the message to produce a new message with the same tag.

For example, let's say that an attacker intercepts the message "Hello" and its authentication tag "ABCD" from a system that uses CBC-MAC with a single key. The attacker can then create a new message "Goodbye" by constructing the following blocks: "Goo", "dby", and "eABCD". *The last block is constructed by XORing the original authentication tag with the final block* of the "Goodbye" message. When this new message is authenticated using CBC-MAC, the system will accept it as valid because it has the same authentication tag as the original message.

This vulnerability exists because of the properties of the XOR operation.