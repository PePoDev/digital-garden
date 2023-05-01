---
{"dg-publish":true,"permalink":"/knowledge/technical/cloud/aws/compute/","dgPassFrontmatter":true}
---

## EKS assume role
```bash
aws eks update-kubeconfig --name <cluster-name> --role-arn arn:aws:iam::<account-id>:role/<role-name> --region ap-southeast-1
```
