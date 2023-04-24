---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/iam/","dgPassFrontmatter":true}
---

## Overview
- Identity
	- Google account
	- Service account
	- Google Group
	- Google Workspace domain
	- Google Identity domain
	- All authenticated users
	- All users
- Roles
	- Basic
		- Viewer, Editor, Owner, and Billing Admin
	- Predefined
		- Compute Admin, Network Admin and etc.
	- Custom
		- Need to manage the permissions that define the custom role you have
		- Custom roles can only be applied to either the project level and organized level
- Condition
	- Specified using Common Expression Language (CEL)

> [!Note]
> It can take up to 80 seconds for such a change to take effect as it propagates. Read more about Google Cloud IAM in the Google Cloud IAMResource Documentation, [Frequently asked questions](https://cloud.google.com/iam/docs/faq).
## Service Account
- Named with an email address
- Use a cryptographic key to access
- Use case: Authenticates seamlessly to the API without embedding any secret keys or credentials in your instance
- Type
	- User-created
	- Built-in (default for Compute Engine and App Engine)
		- automatically created per project with an auto-generated name and email (has `-compute` prefix eg. xxxxxxxx-compute@developer.gserviceaccount.com)
		- Automatically added as an editor role
		- Enabled on all instances by default
		- Scope (legacy, use Role instead)
	- Google APIs service account

![IAM-2023-04-24.png](/img/user/Attachments/IAM-2023-04-24.png)
## Workload Identity Federation
- Grant external identities IAM roles, including impersonating a service account
- Use a short-lived access token instead of a long-lived service account key
- Workload identity pools are collections of related identities for granting fine-grained access
- Workload identity provider describes the relationship between Google and external identity provider
	- AWS
	- Azure AD
	- Okta
	- Kubernetes clusters
	- On-premises AD
## Best practices
- Use the project to group the resources that share the same trust boundary
- Use "principles of least privilege" when grating role
- Audit policies in Cloud Audit Logs: `setiampolicy`
- Audit membership of groups used in polices
- Service accounts
	- Give it a display name that clearly identifies its purpose
	- Establish a naming convention for service accounts
	- Establish key rotation policies and methods
	- Audit with `serviceAccount.keys.list()` method
- Use [[Knowledge/Information Technology/Cloud/Google Cloud/Resource Management#Identity-Aware Proxy (IAP)\|Identity-Aware Proxy (IAP)]] to enforce access control policies for applicators and resources
