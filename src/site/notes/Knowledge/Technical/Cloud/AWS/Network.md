---
{"dg-publish":true,"permalink":"/knowledge/technical/cloud/aws/network/","dgPassFrontmatter":true}
---

## VPC
### EIP
- Elastic IP
- Default 5 EIP per account
### ENI
- Elastic Network Interface - Logical component in a VPC that represents a virtual network card
- Attributes
	- Primary private IPv4, one or more secondary IPv4
	- One EIP per private IPv4
	- One Public IPv4
	- One or more security group
	- A MAC address
- Can create ENI independently and attach them on the fly (move) on EC2 instances for failover
- Bound to a specific AZ
![Network-2023-05-13.png](/img/user/Attachments/Network-2023-05-13.png)
## Route 53
## CloudFront