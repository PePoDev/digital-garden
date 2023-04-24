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
## Secret Manager
- Store API keys, password, or etc
- Multiple version of secrets
- Automate rotation with Cloud Function
- Auditing with Cloud Audit Logs
- Encrypted by default
## VPC Service Control
- Centrally manage multi-tenant service access at scale
- Securely access multi-tenant services
- Establish virtual security perimeters for API-based services
- Maintain an ongoing log of access denials to spot potential malicious activity on Google Cloud resources
- Configure private communication to cloud resources from VPC networks that span cloud and on-premises hybrid deployments using Private Google Access
## Identity-Aware Proxy (IAP)
![Security-2023-04-24.png](/img/user/Attachments/Security-2023-04-24.png)
- A central authorization layer for applications accessed by HTTPS
- You can use an application-level access control model instead of relying on network-level firewalls
- Applications and resources protected by Cloud IAP can only be accessed through the proxy by users and groups with the correct Cloud IAM role
- When you grant a user access to an application or resource by Cloud IAP, they're subject to the fine-grained access controls implemented by the product in use without requiring a VPN
## Shared responsibility
![Security-2023-04-24-1.png](/img/user/Attachments/Security-2023-04-24-1.png)

![Security-2023-04-24-2.png](/img/user/Attachments/Security-2023-04-24-2.png)

![Security-2023-04-24-3.png](/img/user/Attachments/Security-2023-04-24-3.png)

![Security-2023-04-24-4.png](/img/user/Attachments/Security-2023-04-24-4.png)

![Security-2023-04-24-5.png](/img/user/Attachments/Security-2023-04-24-5.png)

![Security-2023-04-24-6.png](/img/user/Attachments/Security-2023-04-24-6.png)

![Security-2023-04-24-7.png](/img/user/Attachments/Security-2023-04-24-7.png)

![Security-2023-04-24-8.png](/img/user/Attachments/Security-2023-04-24-8.png)

![Security-2023-04-24-9.png](/img/user/Attachments/Security-2023-04-24-9.png)

![Security-2023-04-24-10.png](/img/user/Attachments/Security-2023-04-24-10.png)
## Cloud DLP (Data Loss Prevention)
- Keep some information private and confidential
- Redact PII from Google Cloud Service
- Typically focused on specific kinds of attributes
	- Government IDs
	- Credit card numbers
	- Passport number
- Discovery and classification data
	- Personally identifying information (PII)
	- Credentials and secrets
	- Country-specific identifiers
- Automatically mask data
- Measure re-identification risk
## Cloud Armor
![Security-2023-04-24-11.png](/img/user/Attachments/Security-2023-04-24-11.png)

![Security-2023-04-24-12.png](/img/user/Attachments/Security-2023-04-24-12.png)
