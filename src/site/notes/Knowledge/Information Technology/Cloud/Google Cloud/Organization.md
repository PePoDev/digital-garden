---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/organization/","dgPassFrontmatter":true,"noteIcon":"📝"}
---

Created when a Google Workspace or Cloud Identity account creates a Google Cloud Project
## Resource hierarchy
It’s important to understand this resource hierarchy because it directly relates to how policies are managed and applied when you use Google Cloud.
- Organization node (Level 04)
	- Folder (Level 03)
		- Project (Level 02)
			- Resource (Level 01)

> Policies are also inherited downward. This means that if you apply a policy to a folder, it will also apply to all of the projects within that folder.
> 
![Attachments/Pasted image 20230316202934.png](/img/user/Attachments/Pasted%20image%2020230316202934.png)

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