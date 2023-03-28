---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/resource-management/","dgPassFrontmatter":true}
---

## Resource Manager
![Attachments/Pasted image 20230319212043.png](/img/user/Attachments/Pasted%20image%2020230319212043.png)

![Attachments/Pasted image 20230319213129.png](/img/user/Attachments/Pasted%20image%2020230319213129.png)
## Hierarchy
### Function-oriented
![Pasted image 20230327195121.png](/img/user/Attachments/Pasted%20image%2020230327195121.png)
### Environment-oriented
![Pasted image 20230327195150.png](/img/user/Attachments/Pasted%20image%2020230327195150.png)

![Pasted image 20230327195233.png](/img/user/Attachments/Pasted%20image%2020230327195233.png)
## Quotas
- Project quotas prevent runaway consumption in case of error or malicious attack
- Prevent billing spikes or surprises
- Forces sizing consideration and periodic review
- Default
	- 15 VPC networks/project
	- 24 CPUs region/project
## Labels
![Attachments/Pasted image 20230319213915.png](/img/user/Attachments/Pasted%20image%2020230319213915.png)

![Attachments/Pasted image 20230319214044.png](/img/user/Attachments/Pasted%20image%2020230319214044.png)
- Can use with Data Studio to visualize the cost by category
## Cloud Identity
![Pasted image 20230327162202.png](/img/user/Attachments/Pasted%20image%2020230327162202.png)

![Pasted image 20230327162918.png](/img/user/Attachments/Pasted%20image%2020230327162918.png)

### Authentication Options

- Google authentication (No SSO)
- Single sign-on (SSO): Google auth + Cloud Identity as Identity Provider
- Single sign-on (SSO): External Identity Provider

### Password Sync
- G Suite Password Sync (GSPS) is not Password Sync
- Synchronizes user passwords from Active Directory to Cloud Identity as they are changed (in real-time)
- Password Sync intercepts the raw password and applies a salted SHA512 hash
- Encrypted via TLS, the salted hash is sent to Cloud Identity using the Directory API
## Google Cloud Directory Sync (GCDS)
![Pasted image 20230327163125.png](/img/user/Attachments/Pasted%20image%2020230327163125.png)

- One-way synchronization
- Only synchronizes deltas for the fastest possible provisioning
- Configure which users account to sync
## Managed Service for Microsoft AD
- Synchronized forest pattern ![Pasted image 20230328220909.png](/img/user/Attachments/Pasted%20image%2020230328220909.png)
- Sync accounts
- Keeps a trust boundary clear between on-premises and cloud
## Identity-Aware Proxy (IAP)
- A central authorization layer for applications accessed by HTTPS
- You can use an application-level access control model instead of relying on network-level firewalls
- Applications and resources protected by Cloud IAP can only be accessed through the proxy by users and groups with the correct Cloud IAM role
- When you grant a user access to an application or resource by Cloud IAP, they're subject to the fine-grained access controls implemented by the product in use without requiring a VPN
## Billing
### Budget
![Attachments/Pasted image 20230319214248.png](/img/user/Attachments/Pasted%20image%2020230319214248.png)
