---
layout: post
title: RSA digital signature scheme
---
A digital signature is a mathematical scheme for demonstrating the authenticity of a digital message or documents. 
A valid digital signature gives a recipient reason to believe that the message was created by a known sender, that the sender cannot deny having sent the message (authentication and non-repudiation), and that the message was not altered in transit (integrity).**RSA** is one of the first practical public-key cryptosystems and is widely used for secure data transmission. 
In such a cryptosystem, the encryption key is public and differs from the decryption key which is kept secret. 
In RSA, this asymmetry is based on the practical difficulty of factoring the product of two large prime numbers, the factoring problem. RSA is made of the initial letters of the surnames of Ron Rivest, Adi Shamir, and Leonard Adleman, who first publicly described the algorithm in 1977.



RSA DSS approach:



* The hash function is applied to the message.


* A hash code is produced.


* This hash code, along with a random number generated is given as input to the signature function.


* The sender's private key and a global public key is also given as input to the signature function.


* The output of this signature function is concatenated with the original message and sent.


* During reception, the hash function is generated.


* Along with this, the signature is sent to a verification function.


* The verification function depends on the sender's public key and the global public key.


* This is compared with the signature component of the incoming message.


* If they both match, the incoming message is authenticated.

 
This scheme can be implemented for very large numbers (> 1024 bits) in many different languages. I implemented it in C using the 
GMP (**GNU M**uilti **P**recision library ). The **pthread** library of C can also be used to do multithreading. 
 
 
