---
{"dg-publish":true,"permalink":"/knowledge/technical/cloud/aws/compute/","dgPassFrontmatter":true}
---

## EC2
- EC2 = Elastic Compute Cloud
### Instance Type
- AWS has the following naming convention m5.2xlarge`
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
### Security Group
- All inbound traffic is blocked by default
- All outbound traffic is authorized by default
- If your application is not accessible by timeout then it's a security group issue
- If it gives a connection refused error then it's an application error or it's not launched
- Can reference to another security group
### EC2 Instance Connect
- Connect to your EC2 instance within your browser
- Works only out-of-the-box with Amazon Linux 2
- Need to make sure port 22 is still open!
- No need to use your key file that was downloaded
- The “magic” is that a temporary key is uploaded onto EC2 by AWS
### Purchasing Options
- On-Demand Instances
	- Highest cost but no upfront payment
	- Billing per hour
- Reserved Instances
	- up to 72% discount compared to on-demand
	- Reserve specific instance attributes (Instance type, Region, Tenancy, OS)
	- Reservation period: 1 year (+discount), or 3 years (+++discount)
	- Payment option: No upfront (+), Partial Upfront (++), All upfront (+++) 
	- Scope: Regional or Zonal
	- Can buy or sell in Reserved Instance Marketplace
	- Convertible Reserved Instances
		- Can change the EC2 instance type, instance family, OS, scope, and tenancy
		- Up to 66% discount
- Saving Plans (1 & 3 years)
	- Up to 72% same as RI
	- Commit to a certain type of usage ($10/hour for 1 or 3 years)
	- Usage beyond the commit is billed at the On-Demand price
	- Locked to a specific instance family & AWS region
- Spot Instances
	- up to 90% discount (Most cost-efficient instances)
	- Instances can lose at any point in time if your max price is less than the current spot price
- Dedicated Hosts (Book an entire physical server, Control instance placement)
	- Physical server with EC2 instance capacity fully dedicated
	- Allow for the compliance requirements and licenses (BYOL)
	- Purchasing options: On-demand (pay-per-second) and Reserved
	- Most expensive option
- Dedicated Instances (no other customers will share your hardware)
	- Instances run on hardware that's dedicated to you
	- May share hardware with other instances in the same account
	- No control over instance placement (Can move hardware after Stop / Start)
- Capacity Reservations (reserve capacity in a specific AZ for any duration)
	- Reserve on-demand instances capacity in a specific AZ for any duration
	- No time commitment (Create/Cancel anytime), No billing discount
### Spot Instance
- define max spot price and get the instance while the current spot price < max 
- You can choose to Stop or Terminate in 2 minutes grace period
![Compute-2023-05-13-1.png](/img/user/Attachments/Compute-2023-05-13-1.png)
- You can only cancel Spot Instance requests that are open, active, or disabled
- Cancelling Spot Request does not terminate the instance
### Spot Fleets
- Set of Spot Instance + (optional) On-Demand Instance
- The Spot Fleet will try to meet the target capacity with price constraints
	- Define possible launch pools (instance type, OS, zone)
	- Can have multiple launch pools, so the fleet can choose
	- Spot Fleet stops launching instances when reaching capacity or max cost
- Strategies to allocate Spot Instances
	- lowestPrice: from the pool with the lowest price (cost-optimized, short workload)
	- diversified: distributed across all pools (great for availability, long workloads)
	- capacityOptimized: pool with the optimal capacity for the number of instances
	- priceCapacityOptimized (recommended): pools with the highest capacity available, then select the pool with the lowest price (best choice for most workloads)
- Spot Fleets allow us to automatically request Spot Instances with the lowest price
### Placement Groups
- Strategies
	- Cluster: Clusters instances into a low-latency group in a single AZ
	- Spread: spreads instances across underlying hardware (max 7 instances per group per AZ, Critical applications)
	- Partition: Spreads instances across many different partitions (which rely on different sets of racks) within an AZ, Scale to 100s of EC2 instances per group (Hadoop, Cassandra, Kafka)
### Hibernate
- Support instance families: C3, C4, C5, I3, M3, M4, R3, R4, T2, T3, and more
- Root volume must be EBS and encrypted
- Can't be hibernated for more than 60 days
- Not support for bare metal instances
- Ram must be less than 150GB
### AMI
- Amazon Machine Image is a customization of an EC2 instance image
- Built for a specific region (can copy to another region)
![Compute-2023-05-13-2.png](/img/user/Attachments/Compute-2023-05-13-2.png)
### Load Balancer
- Spread the traffic across multiple servers downstream
- Expose a single point of access (DNS) to your application
- Seamlessly handle failures of downstream instances
- SSL termination (Can manage certificates using ACM)
	- Support SNI (Server Name Indication) to solve the problem of loading multiple SSL onto one web server (To serve multiple websites)
		- It's a newer protocol and requires the client to indicate the hostname of the target server in the initial SSL handshake
		- The server will then find the correct certificate or return the default one
		- Only work for ALB & NLB (Newer generation), CloudFront![Compute-2023-05-14.png](/img/user/Attachments/Compute-2023-05-14.png)
- Sticky Sessions (Session affinity)
	- The same client always redirected to the same instance behind a load balancer
	- Works for CLB, ALB, and NLB
	- The `cookie`  used for stickiness has an expiration date you control
	- Enabling stickiness may bring imbalance to the load over the backend
	- Cookie Names
		- Application-based Cookies
			- Custom cookie
				- Generated by the target
				- Can include any custom attributes required by the application
				- Cookie name must be specified individually for each target group
				- Don't use `AWSALB`, `AWSALBAPP`, or `AWSALBTG` (reserved for ELB)
			- Application cookie
				- Generated by the LB
				- The cookie name is `AWSALBAPP`
		- Duration-based Cookies
			- The cookie generated by the LB
			- Cookie name is `AWSALB` for ALB, `AWSELB` for CLB
- Cross Zone Load Balancing
	- ALB
		- Enabled by default (Can disable at the target group)
		- No charges for inter-AZ data
	- NLB & GWLB
		- Disabled by default
		- Pay charges (\&) for inter-AZ data if enabled
	- CLB
		- Disabled by default
		- No charges for inter-AZ data if enabled
	![Compute-2023-05-13-3.png](/img/user/Attachments/Compute-2023-05-13-3.png)
- Connection Draining / Deregistration Delay
	- Time to complete "in-flight requests" while the instance is de-registering or unhealthy
	- Stops sending new requests to the EC2 instance which is de-registering
	- Between 1 to 3600 seconds (default 300s)
	- Can be disabled (set value to 0)
	- Set to low value if your requests are short
- LB Type
	- (Deprecated) Classic Load Balancer (CLB) (HTTP, HTTPS, TCP, SSL)
	- Application Load Balancer (ALB) - layer 7 (HTTP, HTTPS, WebSocket)
		- Routing tables to different target groups (path, hostname, header, or query string)
		- Have a port mapping feature to redirect to a dynamic port in ECS
		- Target groups: ALB can route to multiple target groups
			- EC2
			- ECS tasks
			- Lambda functions
			- IP Address
		- Health checks at the target group level
	- Network Load Balancer (NLB) - layer 4 (TCP, UDP, TSL)
		- Less latency ~100ms (vs 400ms for ALB)
		- One static IP per AZ and support assign EIP
		- Use for extreme performance
		- Not included in the free tier
		- Target groups:
			- EC2
			- IP Addresses - must be private IPs
			- ALB
		- Health checks support the TCP, HTTP, and HTTPS protocols
	- Gateway Load Balancer (GWLB) - layer 3 (IP Protocol)
		- Deploy, scale, and manage a fleet of third-party network virtual appliances in AWS
		- Examples: Firewalls, Intrusion Detection and Prevention Systems, Deep Packet Inspection Systems, payload manipulation, etc
		- Combines the following functions
			- Transparent Network Gateway
			- Load Balancer
		- Uses the `GENEVE` protocol on port 6081
		- Target groups:
			- EC2
			- IP Addresses - Must be private IPs
### Autoscaling Group (ASG)
- Manage the number of EC2 Instances depends on the workload![Compute-2023-05-14-1.png](/img/user/Attachments/Compute-2023-05-14-1.png)
- Automatically register new instances to a load balancer![Compute-2023-05-14-2.png](/img/user/Attachments/Compute-2023-05-14-2.png)
- Re-create an EC2 instance in case a previous one is terminated
- FREE!
- Strategies
	- Dynamic
		- Target Tracking Scaling: Want the average CPU to stay at around 40%
		- Simple / Step Scaling: When the CloudWatch alarm is triggered, then add 2 units
		- Scheduled Actions: Increase the min capacity to 10 at 5 PM on Fridays
	- Predictive
- Good metrics
	- CPU utilization
	- RequestCountPerTarget
	- Average Network In / Out
- Scaling Cooldowns
	- After a scaling activity happens, You are in the cooldown period (default 300 seconds)
	- During the cooldown period, the ASG will not launch or terminate additional instances (Wait for stabilize)
### Launch Template
- Attributes
	- AMI, Instance type
	- EC2 User Data
	- EBS Volumes
	- Security Group
	- SSH Key pair
	- IAM Role for EC2 instances
	- Network + Subnets information
	- LB information
- Min/Max/Desired Capacity
- Scaling Policy
	- Based on CloudWatch alarms (metrics such as Average CPU)
### Launch Configuration
- Deprecated
## EKS
### EKS assumes role
```bash
aws eks update-kubeconfig --name <cluster-name> --role-arn arn:aws:iam::<account-id>:role/<role-name> --region ap-southeast-1
```
