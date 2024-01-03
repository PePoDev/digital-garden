---
{"dg-publish":true,"permalink":"/knowledge/technical/others/ssl/","noteIcon":""}
---

## Overview
![SSL-2023-12-23.png](/img/user/Attachments/SSL-2023-12-23.png)
![SSL-2024-01-03.png](/img/user/Attachments/SSL-2024-01-03.png)
## Root Certificates (trusted root)
Is at the center of the trust model that undergirds Public Key Infrastructure, and by extension SSL/TLS. Let’s start by discussing root programs and work our way out from there.

Every device includes something called a root store. A root store is a collection of pre-downloaded root certificates (and their public keys) that live on the device itself. Generally, the device will use whatever root store is native to its OS, otherwise it might use a third-party root store via an app like a web browser. There are several major root programs of note:

![SSL-2023-12-25.png](/img/user/Attachments/SSL-2023-12-25.png)
## Intermediate certificate
As stated above, Certificate Authorities do not issue server/leaf certificates (end user SSL certificates) directly off of their roots. Those roots are too valuable and there’s just too much risk

So, to insulate themselves, CAs generally issue what is called an intermediate root. The CA signs the intermediate root with its private key, which makes it trusted. Then the CA uses the intermediate certificate’s private key to sign and issue end user SSL certificates. This process can play out several times, where an intermediate root signs another intermediate and then a CA uses that to sign certificate. These links, from root to intermediate to leaf – are the certificate chain
![SSL-2024-01-03-1.png](/img/user/Attachments/SSL-2024-01-03-1.png)
## Certificate Chain
![SSL-2023-12-24-1.png](/img/user/Attachments/SSL-2023-12-24-1.png)
A **certificate chain** is an ordered list of certificates, containing an SSL/TLS Certificate and Certificate Authority (CA) Certificates, that enables the receiver to verify that the sender and all CA's are trustworthy
### Example of an SSL Certificate chain
As an example, suppose you purchase a certificate from the _Awesome Authority_ for the domain `example.awesome`

_Awesome Authority_ isn’t a root certificate authority. Its certificate isn’t directly embedded in your web browser, so it can’t be explicitly trusted.
- _Awesome Authority_ utilizes a certificate issued by _Intermediate Awesome CA Alpha_.
- _Intermediate Awesome CA Alpha_ utilizes a certificate issued by _Intermediate Awesome CA Beta_.
- _Intermediate Awesome CA Beta_ utilizes a certificate issued by _Intermediate Awesome CA Gamma_.
- _Intermediate Awesome CA Gamma_ utilizes a certificate issued by _The King of Awesomeness_.
- _The King of Awesomeness_ is a Root CA. Its certificate is directly embedded in your web browser, therefore it can be explicitly trusted.

In our example, the SSL certificate chain is represented by 6 certificates:
1. End-user Certificate - Issued to: example.awesome; Issued By: Awesome Authority
2. Intermediate Certificate 1 - Issued to: Awesome Authority; Issued By: Intermediate Awesome CA Alpha
3. Intermediate Certificate 2 - Issued to: Intermediate Awesome CA Alpha; Issued By: Intermediate Awesome CA Beta
4. Intermediate Certificate 3 - Issued to: Intermediate Awesome CA Beta; Issued By: Intermediate Awesome CA Gamma
5. Intermediate Certificate 4 - Issued to: Intermediate Awesome CA Gamma; Issued By: The King of Awesomeness
6. Root certificate - Issued by and to: The King of Awesomeness

Certificate 1, the one you purchase from the CA, is your **end-user certificate**. Certificates 2 to 5 are **intermediate certificates**. Certificate 6, the one at the top of the chain (or at the end, depending on how you read the chain), is the root certificate

When you install your end-user certificate for `example.awesome`, you **must** bundle all the intermediate certificates and install them along with your end-user certificate. If the SSL certificate chain is invalid or broken, your certificate won’t be trusted by some devices.
## References
- [The Difference Between Root Certificates and Intermediate Certificates](https://www.thesslstore.com/blog/root-certificates-intermediate/)
- [Root Certificates vs Intermediate Certificates | Venafi](https://venafi.com/blog/what-difference-between-root-certificates-and-intermediate-certificates/)
