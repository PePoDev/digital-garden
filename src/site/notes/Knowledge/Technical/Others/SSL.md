---
{"dg-publish":true,"permalink":"/knowledge/technical/others/ssl/","noteIcon":""}
---

## Root Certificates and Intermediate Certificates
For an SSL certificate to be trusted, that certificate must have been **issued by a CA that’s included in the trusted store of the device that’s connecting**.

If the certificate wasn’t issued by a trusted CA, the connecting device (eg. a web browser) checks to see if the certificate of the issuing CA was issued by a trusted CA. It continues checking until either a trusted CA is found (at which point a trusted, secure connection will be established), or no trusted CA can be found (at which point the device will usually display an error).

![SSL-2023-12-23.png](/img/user/Attachments/SSL-2023-12-23.png)

**What is an Intermediate Certificate?**  
- Any certificate that sits between the SSL/TLS Certificate and the Root Certificate is called a chain or Intermediate Certificate. 
- The **Intermediate Certificate** is the signer/issuer of the SSL/TLS Certificate. 
- The Root CA Certificate is the signer/issuer of the Intermediate Certificate. 
- If the Intermediate Certificate is not installed on the server (where the SSL/TLS certificate is installed) it may prevent some browsers, mobile devices, applications, etc. from trusting the SSL/TLS certificate. 
- In order to make the SSL/TLS certificate **compatible** with all clients, it is necessary that the Intermediate Certificate be installed
### Intermediate CA
Intermediate CA คือใบรับรองกลางที่ผู้ออกใบรับรอง SSL ภายใต้การดูแลของ CA (Certificate Authority) ได้พัฒนาเพิ่มขึ้นมา เพื่อแสดงข้อมูลการเข้ารหัส ถอดรหัสเสมือนเป็นใบรับรองจริง (CA) ในการเข้ารหัสความปลอดภัยระหว่างเครื่องเซิร์ฟเวอร์ เครื่องคอมพิวเตอร์ของผู้ใช้งาน และผู้ให้บริการเว็บบราวเซอร์ อาทิ Internet Explorer , Chrome, Mozilla Firefox, Opera ฯลฯ เป็นต้น

Intermediate CA มีหน้าที่และความสำคัญกับเครื่องเซิร์ฟเวอร์ที่เก็บ Private Key ของRoot CA เป็นอย่างมาก เนื่องจากการทำงานในระบบใบรับรอง SSL นั้น ตั้งอยู่บนความน่าเชื่อถือและความปลอดภัยสูงสุด จึงต้องการจัดเก็บ Private Key ของ Root CAเป็นอย่างดี เพื่อป้องกันพวกแฮคเกอร์ขโมยข้อมูลการเข้ารหัสได้โดยง่าย และด้วยความสำคัญของ Root CA ตามที่ได้กล่าวไป ผู้ให้บริการที่ออกใบรับรอง SSL รายใหญ่ เช่น Verisign , Thawte , Geotrust ฯลฯ จึงมักไม่นำ Root CA มาออนไลน์ให้บริการเข้ารหัสผ่านเว็บบราวเซอร์โดยตรง เพราะมีความเสี่ยงมากเกินไป แต่จะสร้างใบรับรองกลางของเซิร์ฟเวอร์ที่เรียกว่า Intermediate CA ขึ้นมาทำงานแทน จากนั้นก็จัดการปิดเครื่อง Root CA และนำไปเก็บในที่ปลอดภัย และปล่อยให้เครื่อง Intermediate CA ทำหน้าที่ออกใบรับรองดิจิตอลแทน ซึ่งการสร้างไฟล์ Intermediate CA นี้อาจมีหลายระดับชั้น ดังนั้น จึงควรเลือกใช้ไฟล์ Intermediate CA ของผู้ให้บริการ SSL ที่เป็นชุดล่าสุดและเป็นปัจจุบันอยู่เสมอในการติดตั้งบนเครื่องเซิร์ฟเวอร์เดียวกันกับที่ติดตั้ง Root CA ไว้
## Certificate Chain
![SSL-2023-12-24-1.png](/img/user/Attachments/SSL-2023-12-24-1.png)
**What is a Certificate Chain?**
- A **certificate chain** is an ordered list of certificates, containing an SSL/TLS Certificate and Certificate Authority (CA) Certificates, that enables the receiver to verify that the sender and all CA's are trustworthy. 
- The **chain or path begins** with the SSL/TLS certificate, and each certificate in the chain is signed by the entity identified by the next certificate in the chain
### Example of an SSL Certificate chain

As an example, suppose you purchase a certificate from the _Awesome Authority_ for the domain `example.awesome`.

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

Certificate 1, the one you purchase from the CA, is your **end-user certificate**. Certificates 2 to 5 are **intermediate certificates**. Certificate 6, the one at the top of the chain (or at the end, depending on how you read the chain), is the [**root certificate**](https://support.dnsimple.com/articles/what-is-ssl-root-certificate).

When you install your end-user certificate for `example.awesome`, you **must** bundle all the intermediate certificates and install them along with your end-user certificate. If the SSL certificate chain is invalid or broken, your certificate won’t be trusted by some devices.
### Frequently Asked Questions
1. Do I have to install the Root certificate on my server?
    No. The root certificate is usually embedded in your connected device. In the case of web browsers, root certificates are packaged with the browser software.
2. How do I install the Intermediate SSL certificates?
    The procedure to install the Intermediate SSL certificates depends on the web server and the environment where you install the certificate.
    For instance, Apache requires you to bundle the intermediate SSL certificates and assign the location of the bundle to the `SSLCertificateChainFile` configuration. However, NGINX requires you to package the intermediate SSL certificates in a single bundle with the end-user certificate.
    
    We provide a certificate installation wizard which contains installation instructions for several servers and platforms. If you purchase a certificate with us you can [use this wizard to obtain and install the files you need](https://support.dnsimple.com/articles/installing-ssl-certificate) for your server.
    
    If your server isn’t on the wizard, you can still obtain the proper files through it, then follow your web server’s documentation to determine how to properly install your domain certificate and intermediate certificates.
    
3. What happens if I don’t install an Intermediate SSL certificate?
    
    If you don’t install one or more intermediate SSL certificate, you break the certificate chain. That means you create a gap between a specific (end-user or intermediate) certificate and its issuer. When a device can’t find a trusted issuer for a certificate, the certificate and the entire chain, from the intermediate certificate down to the final cerficate, can’t be trusted.
    
    As a result, your final certificate won’t be trusted. Web browsers will display an “Invalid certificate” or “certificate not trusted” error.
    
4. How can I shorten the SSL certificate chain in my browser?
    
    This isn’t possible. The only way to shorten a chain is to promote an intermediate certificate to root. Ideally, you should promote the certificate that represents your Certificate Authority – that way the chain will consist of just two certificates.
    
    Root certificates are packaged with the browser software. The list can only be altered by the browser maintainers.
## References
- [What is the SSL Certificate Chain? - DNSimple Help](https://support.dnsimple.com/articles/what-is-ssl-certificate-chain/)