---
{"dg-publish":true,"permalink":"/knowledge/technical/cloud/aws/compute/","dgPassFrontmatter":true}
---

## EC2
- EC2 = Elastic Compute Cloud
### Instance Type
- AWS has the following naming convention: `m5.2xlarge`
	- m is the instance type
		- General Purpose - T, M, A, Mac
		- Compute Optimized - C
		- Memory Optimized - R, X, z, High memory
		- Storage Optimized - I, D, H
	- 5 is the generation (AWS improves theme over time)
	- 2xlarge is the size
- [AWS Instance Types](https://aws.amazon.com/ec2/instance-types/)
### User-Data
- That script is only run once at the instance the first start
- The EC2 User Data Script runs with the root user
- EC2 user data is used to automate boot tasks such as
	- Installing updates  
	- Installing software  
	- Downloading common files from the internet
	- Anything you can think of
## EKS assume role
```bash
aws eks update-kubeconfig --name <cluster-name> --role-arn arn:aws:iam::<account-id>:role/<role-name> --region ap-southeast-1
```
