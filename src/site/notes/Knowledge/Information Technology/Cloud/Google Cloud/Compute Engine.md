---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/compute-engine/","dgPassFrontmatter":true}
---

## Features
- Machine rightsizing
- Live migrate
- Auto restart
- Global load balancing
- OS patch management
- Per-second billing
- Sustained use discounts
- Committed use discounts
- Preemptible and Spot VMs Up to 91% discount!
## Compute Engine
- vCPU is equal to 1 hardware hyper-thread
- Machine families
	- General purpose (ratio of 0.5 GB to 8 GB of memory per vCPU)
		- E2 (Cost-optimized)
			- Standard (between 2 to 32 vCPUs)
			- Shared-core (0.25 to 1 vCPUs, Context-switching)
			- eg. Web serving, microservices, virtual desktop, small database
		- N2 (Intel), N2D (AMD), N1 (Balanced price/performance)
			- up to 128 vCPUs (Intel), up to 224 vCPUs (AMD)
			- eg. cache, medium database, media/streaming
		- Tau T2D (Scale-out optimized, Best performance/cost for scale-out)
			- up to 60 vCPUs
			- 4 GB of memory per vCPU
			- eg. containerized microservices, large-scale java applications, media transcoding, scale-out workloads
	- Compute-optimized (the highest performance per core)
		- C2 (Ultra-high performance for compute-intensive workloads)
			- 4 to 60 vCPUs
			- up to 240 GB of memory
			- up to 3 TB of local storage
			- Offer all-core turbo
			- eg. compute-bound workloads, gaming (AAA game servers), AI/ML, HPC (High-performance computing), Ad serving, media transcoding
		- C2D
			- 2 to 112 vCPUs
			- 4 GB of memory per vCPU core
			- 3TB of local storage
			- eg. memory-bound workloads, Electronic Design Automation (EDA), high-performance database, media transcoding
	- Memory-optimized (higher memory-to-vCPU ratios)
		- M1
			- up to 4 TB of memory
			- eg. MSSQL Server, in-memory database, in-memory analytics, business warehousing (BW) workloads, genomics analysis
		- M2
			- up to 12 TB of memory
			- eg. Large in-memory databases such as SAP HANA, in-memory analytics, business warehousing (BW) workloads, and genomics analysis
	- Accelerator-optimized
		- A2
			- 12 to 96 vCPUs
			- up to 1360 GB of memory
			- Each A2 machine type has a fixed number (up to 16) of NVIDIA’s Ampere A100 GPUs (40 GB of GPU memory)
			- eg. CUDA (Compute Unified Device Architecture) enabled ML training and inference, HPC, Massively parallelized computation
	- Custom machine type
		- It costs slightly more to use a custom machine type than an equivalent predefined machine type
		- only machine types with 1 vCPU or an even number of vCPUs can be created. Memory must be between 0.9 GB and 6.5 GB per vCPU (by default)
		- you can get more memory per vCPU beyond the 6.5 GB limit. This is referred to as extended memory
- Shielded VMs
	- Secure boot
	- Virtual trusted platform module (vTPM)
	- Integrity monitoring
	- Required shielded image
- Confidential VMs
	- Encrypts data while it's being processed
	- Easy to use with no changes to code or performance compromise
	- Running on N2D with AMD SEV (Secure Encrypted Virtualization)
- Image
	- Premium image indicated in parentheses with a p. eg. RHEL(p)
	- These images will have per-second charges after a one-minute minimum. With the exception of sequel server images, which are charged permanently after a 10-minute minimum.

![Attachments/Pasted image 20230316144325.png](/img/user/Attachments/Pasted%20image%2020230316144325.png)
## Persistent Disks
- Standard and SSD PDs scale in performance for each GB
- Resize or migrate instances with no downtime
- Local SSD can create up to 8 partitions per instance with 375 GB (Total 3TB)
- Standard and non-local SSD can be sized up to 257 TB for each instance
- Attach read-only for multiple VMs
![Pasted image 20230325153309.png](/img/user/Attachments/Pasted%20image%2020230325153309.png)
## Networking
- Network throughput scales at 2 Gbps per vCPU
	- Max 32 Gbps with 16 vCPU
- Up to 8 NICs connected to different network
- Can't modify after creation
## Pricing
- Per-second billing, with a minimum of 1 minute
- Resource-based pricing: each vCPU and memory is billed separately
- Discounts
	- Sustained use
	- Committed use
		- up to 57% for most machine types
		- up to 70% for memory-optimized machine types
	- Preemptible VM
		- Up to 91%
		- 30-second termination warning, but not guaranteed
		- 24 hours max
		- no live migration; no auto restart
	- Spot VM
		- the latest version of preemptible
		- no maximum runtime
		- no live migration; no auto restart
- Recommendation Engine
	- Notifies you of underutilized instances
	- recommendations for the new instance will appear 24 hours after the instance has been created
- Free usage limits
	- Sustained use discounts are automatic discounts that you get for running

![Attachments/Pasted image 20230316140034.png](/img/user/Attachments/Pasted%20image%2020230316140034.png)
![Attachments/Pasted image 20230316140220.png](/img/user/Attachments/Pasted%20image%2020230316140220.png)
![Attachments/Pasted image 20230316140359.png](/img/user/Attachments/Pasted%20image%2020230316140359.png)
### Managed Instance Groups
- Deploy identical instances based on the instance template
- The instance group can be resized
- The manager ensures all instances are RUNNING
- Typically used with autoscaler
- Can be a single zone or regional
