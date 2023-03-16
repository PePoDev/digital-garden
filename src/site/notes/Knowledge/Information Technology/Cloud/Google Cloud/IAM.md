---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/iam/","dgPassFrontmatter":true,"noteIcon":"📝"}
---

## Type of IAM Role
- Basic
	- Viewer, Editor, Owner, and Billing Admin
- Predefined
	- Compute Admin, Network Admin and etc.
- Custom
	- Need to manage the permissions that define the custom role you have
	- Custom roles can only be applied to either the project level and organized level

> [!Note]
> It can take up to 80 seconds for such a change to take effect as it propagates. Read more about Google Cloud IAM in the Google Cloud IAMResource Documentation, [Frequently asked questions](https://cloud.google.com/iam/docs/faq).
## Service Account
- Named with an email address
-  Use a cryptographic key to access
## Cloud Identity
- Login and manage resources using the same credentials used in existing Active Directory or LDAP systems
- Google Admin console can be used to disable user accounts and remove them from groups when they leave
- Available in free and premium editions
- Already available to Google Workspace customers in the Google Admin console
