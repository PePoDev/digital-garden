---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/resource-management/","dgPassFrontmatter":true}
---

## Resource Manager
![Attachments/Pasted image 20230319212043.png](/img/user/Attachments/Pasted%20image%2020230319212043.png)

![Attachments/Pasted image 20230319213129.png](/img/user/Attachments/Pasted%20image%2020230319213129.png)
## Organization
- Created when using G Suite or Use Google Cloud Identity
- Fixed ID but can change the name
### Organization Policy
- Centralized constraints on all resources created in Organization
## Hierarchy
### Function-oriented
![Pasted image 20230327195121.png](/img/user/Attachments/Pasted%20image%2020230327195121.png)
### Environment-oriented
![Pasted image 20230327195150.png](/img/user/Attachments/Pasted%20image%2020230327195150.png)

![Pasted image 20230327195233.png](/img/user/Attachments/Pasted%20image%2020230327195233.png)
## Labels
![Attachments/Pasted image 20230319213915.png](/img/user/Attachments/Pasted%20image%2020230319213915.png)

![Attachments/Pasted image 20230319214044.png](/img/user/Attachments/Pasted%20image%2020230319214044.png)
- Can use with Data Studio to visualize the cost by category
## Cloud Identity
![Pasted image 20230415221925.png](/img/user/Attachments/Pasted%20image%2020230415221925.png)

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
## Billing
### Billing Account
- pays for project resources
- A billing account is linked to one or more projects
- A project that didn't link with a billing account can use only free resources
- Charged automatically or invoiced every month or at a threshold limit
- Subaccounts can be used for separate billing for projects
- Types
	- Self-Serve: Billed directly to Credit Card or Bank Account
	- Invoiced: Generate invoices (Used by large enterprises)
### Budgets & Alerts
![Attachments/Pasted image 20230319214248.png](/img/user/Attachments/Pasted%20image%2020230319214248.png)
### Billing export
- Export to BigQuery
- Can use Data Studio to visualize data
- File export to CSV and JSON is deprecated
### Reports
- Visual tool for monitor expenditure based on a project or services
### Quotas
- Project quotas prevent runaway consumption in case of error or malicious attack
- Prevent billing spikes or surprises
- Forces sizing consideration and periodic review
- Default
	- 15 VPC networks/project
	- 24 CPUs region/project
- Type of quotas
	- Rate
		- GKE API: 1000 requests per 100 seconds
	- Allocation
		- 5 networks per project
- Can change by requesting Google Cloud support
