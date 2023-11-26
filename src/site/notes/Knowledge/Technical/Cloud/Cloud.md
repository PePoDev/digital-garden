---
{"dg-publish":true,"sticker":"1f327-fe0f","permalink":"/knowledge/technical/cloud/cloud/","dgPassFrontmatter":true}
---

## Cloud Providers

- **[[Knowledge/Technical/Cloud/AWS/AWS\|AWS]]**
- **[[Knowledge/Technical/Cloud/Azure/Azure\|Azure]]**
- **[[Knowledge/Technical/Cloud/Google Cloud/Google Cloud\|Google Cloud]]**


## Links
- [Cloud Academy](https://cloudacademy.com/dashboard/)
- [Tutorials Dojo](https://tutorialsdojo.com/)
- [Whizlabs](https://www.whizlabs.com/)
## Why Cloud?
- Refresh cycle (buy new hardware every 3 years?)
- Flexibility (on-demand capacity, cost optimization)
- Elasticity (scalable, pay what you go)
- Security
## Digital Transfomation
- When an organization uses new digital technologies, such as public, private, and hybrid cloud platforms to create or modify business processes, culture, and customer experiences to meet the needs of changing business and market dynamics
## Cloud Model
- Private Cloud (Colocation, Virtualized data center)
- Public Cloud (Google Cloud, AWS, Azure)
- Hybrid Cloud
- Multi-Cloud

> [!note]
>  81% of organizations are working with two or more public cloud providers
>  (Gartner)
## Cloud Service Models
- On-premises (Owning a car)
- IaaS (Leasing a car)
	- Raw compute
	- Storage
	- Network capability
	- pay for what they allocate
- PaaS (Taking a taxi)
	- bind code to the library
	- pay for what they use
- SaaS (Going by bus)
## Total Cost of Ownership
> [!NOTE]
>  Total Cost of Owner = Capital Expense + Operational Expense

![Pasted image 20230315225212.png](/img/user/Attachments/Pasted%20image%2020230315225212.png)
### CapEx & OpsEx
- Capital expenditures (CapEx)
	- Upfront business expenses put toward fixed assets
- Operation expenditures (OpEx)
	- Recurring costs for a more immediate benefit

![Pasted image 20230422185001.png](/img/user/Attachments/Pasted%20image%2020230422185001.png)

![Pasted image 20230422185204.png](/img/user/Attachments/Pasted%20image%2020230422185204.png)

![Pasted image 20230315230145.png](/img/user/Attachments/Pasted%20image%2020230315230145.png)
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
## Cloud change patterns
- Move applications first and then change them
- Change applications before they move
- Invent in greenfield
	- building an entirely new infrastructure and applications in the cloud
- Invent in brownfield
	- invent a new application in the cloud environment that will replace an existing legacy application that remains on premises
- Move applications without any changes
## NORTH-SOUTH and EAST-WEST
- NORTH-SOUTH traffic is a server-client traffic
- EAST-WEST traffic is a server-server traffic
