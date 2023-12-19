---
{"dg-publish":true,"permalink":"/knowledge/technical/cloud/google-cloud/organization/","noteIcon":""}
---

Created when a Google Workspace or Cloud Identity account creates a Google Cloud Project
## Resource hierarchy
It’s important to understand this resource hierarchy because it directly relates to how policies are managed and applied when you use Google Cloud.
- Organization node (Level 04)
	- Folder (Level 03)
		- Project (Level 02)
			- Resource (Level 01)

> Policies are also inherited downward. This means that if you apply a policy to a folder, it will also apply to all of the projects within that folder.

![Organization-2023-04-24.png](/img/user/Attachments/Organization-2023-04-24.png)

> [!note]
> G Suite is now Google Workspace
### Role
- Workspace or Cloud Identity super administrator
	- Assign the organization admin role to some user
	- Be the point of contact in case of recovery issues
	- Control the lifecycle of the workspace or Cloud Identity account and Organization resource
- Organization admin
	- Define IAM policies
	- Determine the structure of the resource hierarchy
	- Delegate responsibility over critical components such as Networking, Billing, and Resource Hierarchy through the IAM roles
- Project Creator
	- Controls project creation
	- control over who can create projects
## Cloud Identity
- Login and manage resources using the same credentials used in existing Active Directory or LDAP systems
- Google Admin console can be used to disable user accounts and remove them from groups when they leave
- Available in free and premium editions
- Already available to Google Workspace customers in the Google Admin console
### Single sign-on (SSO)
- Use Cloud Identity to configure SAML SSO
- If SAML2 isn't supported, use a third-party solution (ADSF, Ping, or Okta)
## Google Cloud Directory Sync
- Scheduled one-way sync
- Sync existing users from Microsoft AD or LDAP
