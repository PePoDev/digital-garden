---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/security/","dgPassFrontmatter":true}
---

## Cloud KMS
- Create and manage cryptographic keys (Symmetric and asymmetric)
- Control their use in your applications and GCP services
- Provides an API to encrypt, decrypt, or sign data
- Use existing cryptographic keys created on-premises
- Integrates with almost all GCP services that need data encryption
- Mode
	- Google Managed
	- Customer managed - using Cloud Key Management Service
	- Customer supplied - using the key created and managed by the customer
## VPC Service Control
- Centrally manage multi-tenant service access at scale
- Securely access multi-tenant services
- Establish virtual security perimeters for API-based services
- Maintain an ongoing log of access denials to spot potential malicious activity on Google Cloud resources
- Configure private communication to cloud resources from VPC networks that span cloud and on-premises hybrid deployments using Private Google Access
## Identity-Aware Proxy (IAP)
![Pasted image 20230415221844.png](/img/user/Attachments/Pasted%20image%2020230415221844.png)
- A central authorization layer for applications accessed by HTTPS
- You can use an application-level access control model instead of relying on network-level firewalls
- Applications and resources protected by Cloud IAP can only be accessed through the proxy by users and groups with the correct Cloud IAM role
- When you grant a user access to an application or resource by Cloud IAP, they're subject to the fine-grained access controls implemented by the product in use without requiring a VPN
## Shared responsibility
![Pasted image 20230415215541.png](/img/user/Attachments/Pasted%20image%2020230415215541.png)

![Pasted image 20230415215754.png](/img/user/Attachments/Pasted%20image%2020230415215754.png)

![Pasted image 20230415215814.png](/img/user/Attachments/Pasted%20image%2020230415215814.png)

![Pasted image 20230415221443.png](/img/user/Attachments/Pasted%20image%2020230415221443.png)

![Pasted image 20230415221454.png](/img/user/Attachments/Pasted%20image%2020230415221454.png)

![Pasted image 20230415221512.png](/img/user/Attachments/Pasted%20image%2020230415221512.png)

![Pasted image 20230415222936.png](/img/user/Attachments/Pasted%20image%2020230415222936.png)

![Pasted image 20230415223041.png](/img/user/Attachments/Pasted%20image%2020230415223041.png)

![Pasted image 20230415223030.png](/img/user/Attachments/Pasted%20image%2020230415223030.png)

![Pasted image 20230415223117.png](/img/user/Attachments/Pasted%20image%2020230415223117.png)
## Cloud DLP (Data Loss Prevention)
- redact PII from Google Cloud Service
## Cloud Armor
![Pasted image 20230415222837.png](/img/user/Attachments/Pasted%20image%2020230415222837.png)

![Pasted image 20230415222856.png](/img/user/Attachments/Pasted%20image%2020230415222856.png)
