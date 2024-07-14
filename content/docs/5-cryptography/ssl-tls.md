---
weight: 60
title: "SSL/TLS"
---

# SSL/TLS

SSL/TLS provides a layer that sits on top of our transport layer and provides end-to-end security.

## TLS Handshake via RSA

1. The browser initiates a TCP connection to the server.

2. The browser generates a random number called RB and sends it to the server along with a list of cryptographic protocols it supports.

3. The server responds by generating its own random number called RS and selecting a cipher suite to use for the session.

4. The server sends its digital certificate to the browser. This certificate contains the server's public key and some information about the server's identity.

5. The browser verifies the certificate to make sure it was issued by a trusted certificate authority and that it is valid for the domain it is connecting to.

6. The browser generates a long secret key called the "Premaster Secret" (PS) and encrypts it using the server's public key.

7. The server uses its private key to decrypt the Premaster Secret. The server and the client use the Premaster Secret along with the random numbers RB and RS, to derive a set of symmetric encryption and MAC keys.

8. The browser and server exchange MACs computed over the entire dialogue up to this point. If the MACs are good, the browser continues with the connection.

9. All subsequent communication between the browser and server is encrypted using the agreed-upon symmetric encryption keys (e.g., AES128) and MACs.

{{< hint info >}}

Messages are also numbered to prevent replay attacks.

{{< /hint >}}

{{< youtube 86cQJ0MMses >}}

## TLS Handshake via Diffie Hellman

1. The server generates a random number a and public parameters, including g^a mod p, where p and g are large prime numbers. The server signs these parameters with its private key and sends them to the browser.

2. The browser verifies the server's signature to make sure the parameters haven't been tampered with.

3. The browser generates a random number b and computes g^(ab) mod p using the server's public parameters. This result is called the "shared secret" or PS.

4. The browser sends g^b mod p to the server.

5. The server also computes PS using its own random number a and the browser's public parameters.

6. From the shared secret PS, the random number RB, and the server's random number RS, the browser and server derive symmetric encryption and MAC keys (CB, CS, IB, IS) just like in the previous example.

7. The browser and server exchange MACs computed over the entire dialogue up to this point. If the MACs are good, the browser continues with the connection.

8. All subsequent communication between the browser and server is encrypted using the agreed-upon symmetric encryption keys and MACs. Messages are also numbered to prevent replay attacks.
