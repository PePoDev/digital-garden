---
{"dg-publish":true,"permalink":"/knowledge/technical/cloud/aws/aws/","dgPassFrontmatter":true}
---

IAM: Users & Groups

• IAM = Identity and Access Management, Global service  
• Root account created by default, shouldn’t be used or shared  
• Users are people within your organization, and can be grouped  
• Groups only contain users, not other groups  
• Users don’t have to belong to a group, and user can belong to multiple groupsIAM: Users & Groups

• IAM = Identity and Access Management, Global service  
• Root account created by default, shouldn’t be used or shared  
• Users are people within your organization, and can be grouped  
• Groups only contain users, not other groups  
• Users don’t have to belong to a group, and user can belong to multiple groups
---
dg-publish: true
sticker: 1f325-fe0f
---
## Links
- [AWS Cloud Solutions Architect Professional Certificate | Coursera](https://www.coursera.org/professional-certificates/aws-cloud-solutions-architect)
- [AWS training and certification](https://www.aws.training/Certification)
- [AWS Pearson VUE free-retake](https://home.pearsonvue.com/aws/free-retake)
- [AWS Well-Architected Labs](https://wellarchitectedlabs.com/operational-excellence/100_labs/100_inventory_patch_management/1_intro/)
- [AWS Control Tower Workshop](https://controltower.aws-management.tools/core/accountfactory/)
- [AWS Solutions Architect Associate | Udemy](https://opn.udemy.com/course/aws-certified-solutions-architect-associate-saa-c03/learn/lecture/13528014?start=15#overview)
- [AWS Community Builders Content Reporting Tool](https://www.0100000101010111010100110110001101100010.com/#/)
## Tools
- [Amazon EC2 Instance Comparison](https://instances.vantage.sh/)
- [AWS Pricing Calculator](https://calculator.aws/#/)
- [AWS Outpost Visual 3D](https://apps.kaonadn.net/5181491956940800/AWSOutpost/index.html?lang=en#Catalog)
- [AWS Edge Cloud Global Visual](https://apps.kaonadn.net/5181491956940800/index.html)
## Certificates

- [x] AWS Cloud Practitioner #certificate
- [/] AWS Solution Architect Associate #certificate 🔼
- [ ] AWS Developer Associate #certificate
- [ ] AWS SysOps Administrator Associate #certificate
- [/] AWS Solution Architect Professional #certificate
- [ ] AWS DevOps Engineer Professional #certificate
- [ ] AWS Advanced Networking Specialist #certificate
- [ ] AWS Data Analytics Specialist #certificate
- [ ] AWS Database Specialist #certificate
- [ ] AWS Machine Learning Specialist #certificate
- [ ] AWS Security Specialist #certificate
- [ ] AWS SAP on AWS Specialist #certificate
## Backlink

- [[Knowledge/Technical/Cloud/AWS/Analytic\|Analytic]]
- [[Knowledge/Technical/Cloud/AWS/Automation\|Automation]]
- [[Knowledge/Technical/Cloud/AWS/Compute\|Compute]]
- [[Knowledge/Technical/Cloud/AWS/IAM\|IAM]]
- [[Knowledge/Technical/Cloud/AWS/Monitoring\|Monitoring]]
- [[Knowledge/Technical/Cloud/AWS/Network\|Network]]
- [[Knowledge/Technical/Cloud/AWS/Security\|Security]]
- [[Knowledge/Technical/Cloud/AWS/Storage\|Storage]]
- [[Knowledge/Technical/Cloud/AWS/Well-Architect\|Well-Architect]]


## AWS Availability Zones
- Each region has many availability zones (usually 3, min is 3, max is 6). Example: 
	- ap-southeast-2a
	- ap-southeast-2b
	- ap-southeast-2c
- Each availability zone (AZ) is one or more discrete data centers with redundant power, networking, and connectivity
- They’re separate from each other, so that they’re isolated from disasters
- They’re connected with high bandwidth, ultra-low latency networking
## AWS Points of Presence (Edge Locations)
- Amazon has 216 Points of Presence (205 Edge Locations & 11 Regional Caches) in 84 cities across 42 countries
- Content is delivered to end users with lower latency
![AWS-2023-05-01.png](/img/user/Attachments/AWS-2023-05-01.png)
## AWS Services
### Global Services
- IAM
- CloudFront
- Route 53
- WAF
- ACM
### Region-scoped Services
- VPC
- EC2
- Beanstalk
- Lambda
- Rekognition