---
{"dg-publish":true,"permalink":"/knowledge/technical/cloud/google-cloud/resource-management/","dgPassFrontmatter":true}
---

## Resource Manager
![Resource Management-2023-04-24.png](/img/user/Attachments/Resource%20Management-2023-04-24.png)

![Resource Management-2023-04-24-1.png](/img/user/Attachments/Resource%20Management-2023-04-24-1.png)
## Organization
- Created when using G Suite or Use Google Cloud Identity
- Fixed ID but can change the name
### Organization Policy
- Centralized constraints on all resources created in Organization
## Hierarchy
### Function-oriented
![Resource Management-2023-04-24-2.png](/img/user/Attachments/Resource%20Management-2023-04-24-2.png)
### Environment-oriented
![Resource Management-2023-04-24-3.png](/img/user/Attachments/Resource%20Management-2023-04-24-3.png)

![Resource Management-2023-04-24-4.png](/img/user/Attachments/Resource%20Management-2023-04-24-4.png)
## Labels
![Resource Management-2023-04-24-5.png](/img/user/Attachments/Resource%20Management-2023-04-24-5.png)

![Resource Management-2023-04-24-6.png](/img/user/Attachments/Resource%20Management-2023-04-24-6.png)
- Can use with Data Studio to visualize the cost by category
## Cloud Identity
![Resource Management-2023-04-24-7.png](/img/user/Attachments/Resource%20Management-2023-04-24-7.png)

![Resource Management-2023-04-24-8.png](/img/user/Attachments/Resource%20Management-2023-04-24-8.png)

![Resource Management-2023-04-24-9.png](/img/user/Attachments/Resource%20Management-2023-04-24-9.png)
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
![Resource Management-2023-04-24-10.png](/img/user/Attachments/Resource%20Management-2023-04-24-10.png)

- One-way synchronization
- Only synchronizes deltas for the fastest possible provisioning
- Configure which users account to sync
## Managed Service for Microsoft AD
- Synchronized forest pattern ![Resource Management-2023-04-24-11.png](/img/user/Attachments/Resource%20Management-2023-04-24-11.png)
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
![Resource Management-2023-04-24-12.png](/img/user/Attachments/Resource%20Management-2023-04-24-12.png)
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
