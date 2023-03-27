---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/cloud/","dgPassFrontmatter":true}
---

## Why Cloud?
- Refresh cycle (buy new hardware every 3 years?)
- Flexibility (on-demand capacity, cost optimize)
- Elasticity (scalable, pay what you go)
- Security
## Cloud Model
- Colocation
- Virtualized data center
- Container-based architecture (Google Cloud)
## IaaS and PaaS
### Infrastructure as a Service
- Raw compute
- Storage
- Network capability
- pay for what they allocate
### Platform as a Service
- bind code to the library
- pay for what they use
## Total Cost of Ownership
> [!note]
>  Total Cost of Owner = Capital Expense + Operational Expense

![Attachments/Pasted image 20230315225212.png](/img/user/Attachments/Pasted%20image%2020230315225212.png)
### CapEx & OpsEx
![Attachments/Pasted image 20230315230145.png](/img/user/Attachments/Pasted%20image%2020230315230145.png)
## Migration strategies
### Google
![Pasted image 20230324010320.png](/img/user/Attachments/Pasted%20image%2020230324010320.png)

- Access - Evaluate your environment
	- Input
		- Business objectives
		- Key stakeholders
		- Technical assumptions
		- Security approval for tolling
	- Output 
		- Workload grouping
		- First-mover workloads identified
		- Refined TCO/ROI analysis
		- High-level effort estimations
- Prepare - Understand the platform
- Migrate - Move virtual machines
- Optimize - Tune your operations and save on costs
### AWS
![Pasted image 20230324133737.png](/img/user/Attachments/Pasted%20image%2020230324133737.png)

- Retire - shut down the servers within that application stack
- Retain - keep in your source environment or applications that you are not ready to migrate
- Rehost (lift and shift) - move your applications from your source environment to the AWS Cloud without making any changes to the application
- Relocate - transfer a large number of servers, comprising one or more applications, at a given time from an on-premises platform to a cloud version of the platform
- Repurchase (drop and shop) - replace your application with a different version or product
- Replatform (lift, tinker, and shift or lift and reshape) - move the application to the cloud, and you introduce some level of optimization in order to operate the application efficiently, reduce costs, or take advantage of cloud capabilities
- Refactor or re-architect - move an application to the cloud and modify its architecture by taking full advantage of cloud-native features to improve agility, performance, and scalability
### Automated discovery options
- Discovery
- Estimate cost
- Access your workload portfolio
- Tools
	- CloudPhysics
	- Cloudamize
	- [StratoZone](https://cloud.google.com/migrate/stratozone/docs/about-stratozone)
		- Supports multiple hypervisors/CSPs
		- Scans networks & queries VMs without the agent
		- Deploys in 45 minutes, gives results in <1 week
		- Provides inventory, TCO projections, right-sizing recommendations, dependency analysis, etc
### Invent in brownfield

### Invent in greenfield

## NORTH-SOUTH and EAST-WEST
- NORTH-SOUTH traffic is a server-client traffic
- EAST-WEST traffic is a server-server traffic
## Cloud Providers
- [[Knowledge/Information Technology/Cloud/Google Cloud/Google Cloud\|Google Cloud]]
- [[Knowledge/Information Technology/Cloud/AWS/AWS\|AWS]]
- [[Knowledge/Information Technology/Cloud/Azure/Azure\|Azure]]