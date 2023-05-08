---
{"dg-publish":true,"permalink":"/knowledge/technical/cloud/aws/iam/","dgPassFrontmatter":true}
---

## IAM: Users & Groups
- IAM = Identity and Access Management, Global service
- Root accounts created by default, shouldn’t be used or shared
- Users are people within your organization and can be grouped
- Groups only contain users, not other groups
- Users don’t have to belong to a group, and users can belong to multiple groups

![IAM-2023-05-01.png](/img/user/Attachments/IAM-2023-05-01.png)
## IAM Role for Service Account (IRSA)
- Some AWS services will need to perform actions on your behalf
- To do so, we will assign permissions to AWS services with IAM Roles
## IAM Credentials Report (account-level)
- Report all user account's users and the status of their various credentials
## IAM Access Advisor (user-level)
- Access advisor shows the service permissions granted to a user and when those services were last accessed
- You can use this information to revise your policies