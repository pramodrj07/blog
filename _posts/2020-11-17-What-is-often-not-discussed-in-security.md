---
layout: post
title:  "What is often not discussed in Security"
author: pramod
categories: [ Security ]
image: assets/images/security.jpg
tags: featured
---
While designing a system that is optimal for your application, one would probably prioritize and emphasize on the cool features, modern platforms, scalability and resiliency. While the security aspect may be considered as a second priority, it would be good to understand it at a deeper level and best pratices in industry.

Often unheard but extremely important terminology in security is "Hardware Security Module". Hardware Security Module(HSM) are often specialized hardware devices that can store, protect and manage the digital keys. They are capable of handling encryption, decryption, authentication, signature functions such as signing certificates and a lot of other cryptographic funtions.

We will find that HSMs are deployed in all the corporate and Banking sectors which have multiple applications running in a data center. The application will request HSMs for keys while initializing, signing data or for certificates. The secure feature of HSM is that the keys(private keys) that are stored in it will never ever be exposed to the outside world. An application can only send a request for the data to be signed but will never get its hands on the private key. This is usually done with a parameter called "handle". The keys are tamper proof as well. For example, if there is a visible sign of tampering, the HSM would delete that specific key rather than exposing it outside or perform any related operation. How cool is that?

My experience in integrating a Hardware Security Module(TPM) into the Cloud has led me to question and investigate the security aspect everytime I work on a new project. I would probably spend an entire day in discussion when a developer says that the secrets and keys are on test/development server. 

Checkout my work here on [here][confluence-page]

[confluence-page]: https://wiki.onap.org/display/DW/Integration+of+SoftHSM2+with+HW-Plugins