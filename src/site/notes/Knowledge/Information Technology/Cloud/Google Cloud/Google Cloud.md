---
{"tag":"gcp, cloud, hard-skill","dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/google-cloud/","dgPassFrontmatter":true}
---

## Links
- https://www.webassessor.com/wa.do?page=enterCatalog&tabs=7
- https://partner.cloudskillsboost.google
- https://www.cloudskillsboost.google/profile/paths
- https://rsvp.withgoogle.com/events/partner-learning/google-cloud-certifications
- https://cloud.google.com/products/calculator
- https://partner.cloudskillsboost.google/course_sessions/2441031/video/351448
## Certificates
- [ ] Cloud Digital Leader
- [ ] Associate Cloud Engineer
- [ ] Professional Cloud Architect
- [ ] Professional Cloud Developer
- [ ] Professional Data Engineer
- [ ] Professional Cloud Database Engineer
- [ ] Professional Cloud Network Engineer
- [ ] Professional Cloud Security Engineer
- [ ] Professional Cloud DevOps Engineer
- [ ] Google Workspace Administrator
- [ ] Machine Learning Engineer

> [!tip]+
> Cloud computing is a way of using information technology (IT) that has these five equally important traits.
> First, customers get computing resources that are on-demand and self-service.
> Second, customers get access to those resources over the internet, from anywhere they have a connection.
> Third, the cloud provider has a big pool of those resources and allocates them to users out of that pool. That allows the provider to buy in bulk and pass the savings on to the customers.
> Fourth, the resources are elastic–which means they’re flexible, so customers can be.
> Finally, customers pay only for what they use, or reserve as they go.

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

## Google Cloud Network
Google has invested billions of dollars over many years to build it. This network is designed to give customers the highest possible throughput and lowest possible latencies for their applications by leveraging more than 100 content caching nodes worldwide. These are locations where high-demand content is cached for quicker access, allowing applications to respond to user requests from the location that will provide the quickest response time.
Google Cloud’s infrastructure is based in five major geographic locations:
- North America
- South America
- Europe
- Asia
- Australia.

> Latency: measures the time a packet of information takes to travel from its source to its destination.

> Google Cloud currently supports 103 zones in 34 regions. (up-to-date at cloud.google.com/about/locations)

>  Altogether, existing data centers use roughly 2% of the world’s electricity.

> Google's data centers were the first to achieve ISO 14001 certification, which is a standard that maps out a framework for an organization to enhance its environmental performance by improving resource efficiency and reducing waste.

![Pasted image 20230209232307.png](/img/user/Attachments/Pasted%20image%2020230209232307.png)

- In our founding decade, Google became the first major company to be carbon neutral.
- In our second decade, we were the first company to achieve 100% renewable energy.
- By 2030, we aim to be the first major company to operate completely carbon-free.

![Pasted image 20230209232503.png](/img/user/Attachments/Pasted%20image%2020230209232503.png)

## Google Infrastructure Security 
1. Hardware security layer
	- Hardware design and provenance
	- Secure boot stack
	- Premises Security
2. Service deployment layer
	- Encryption of inter-service communication
3. User identity later
4. Storage services layer
	- Encryption at rest
5. Internet communication layer
	- Google Front End (GFE)
	- Denial of Service (DoS) protection
6. Operational Security layer
	- Intrusion detection
	- Reducing insider risk
	- Employee Universal Second Factor (U2F) use
	- Software development 

## Pricing & Billing

- Google was the first major cloud provider to deliver per-second billing.
- Automatically applied sustained-use discounts, which are automatic discounts that you get for running a virtual machine instance for a significant portion of the billing month. Specifically, when you run an instance for more than 25% of a month, Compute Engine automatically gives you a discount for every incremental minute you use for that instance.

https://cloud.google.com/products/calculator

![Pasted image 20230212225053.png](/img/user/Attachments/Pasted%20image%2020230212225053.png)
### Quotas
Applied at the project level
- Rate quota (reset after a specific time)
- Allocation quota (governs the number of resources)
### Project identity
- Project ID
	- Globally unique
	- Mutable during creation
	- Immutable after creation
- Project name
	- Need not be unique
	- Chosen by user
	- Mutable
- Project number
	- Globally unique
	- Assigned by Google Cloud
	- Immutable

### Resource Manager Tool
Designed to programmatically help to manage projects
- Gather a list of projects
- Create new projects
- Update existing projects
- Delete projects
- Recover previously deleted projects
- Access through RPC API and REST API
### Interacting with Google Cloud
1. Google Cloud console
2. Cloud SDK and Cloud Shell
3. APIs
4. Cloud Mobile App
## Google Cloud Services
- [[Knowledge/Information Technology/Cloud/Google Cloud/IAM\|IAM]]
- [[Knowledge/Information Technology/Cloud/Google Cloud/Network\|Network]]
- [[Knowledge/Information Technology/Cloud/Google Cloud/Compute Engine\|Compute Engine]]
- [[Knowledge/Information Technology/Cloud/Google Cloud/Storage\|Storage]]
### Cloud DNS
- 100% Uptime SLA
### App Engine

- Standard
  - Run in seconds
  - no SSH access
  - no write on disk (maybe /tmp available)
  - network access via App Engine
  - pay per instance class with automatic shutdown
- Flexible
  - Run in minutes
  - SSH accessible
  - ephemeral disk
  - Can access without App Engine network
  - Pay per hour and no automatic shutdown

### Cloud Run
- A managed to compute platform that can run the stateless containers
- Serverless, removing the need for infrastructure management
- Built on Knative, an open API and runtime environment built on Kubernetes
- Can automatically scale up and down from zero almost instantaneously charging only for the resources used

### Cloud Endpoints
- Distributed API management system
- Provides an API console, hosting, logging, monitoring, and other features
- Use with any APIs that support the OpenAPI specification
- Supports applications running in App Engine, GKE, and Compute Engine
- Clients include Android, iOS, and Javascript

### API Gateway
- Backend implementations can vary for a single service provider
- Provide secure access to your backend services through a well-defined REST API
- Clients consume your REST APIs to implement standalone apps

### Apigee  Edge
- Specific focus on business problems like rate limiting quotas and analytics
- Many Apigee Edge users provide a software service to other companies
- Backend services for Apigee Edge don't need to be in Google Cloud

### Cloud Source Repository
- Git repository
- Work with Google services
-  allows Google Cloud diagnostics tools, like Debugger and Error Reporting

### Cloud Function
- Cloud Functions is a lightweight, event-based, asynchronous compute solution that allows you to create small, single-purpose functions that respond to cloud events, without the need to manage a server or a runtime environment.


### Logging

### Monitoring

![Attachments/Pasted image 20230307225538.png](/img/user/Attachments/Pasted%20image%2020230307225538.png)

#### Four Golden Signals
- Latency
	- Page load latency
	- Number of requests waiting for a thread
	- Query duration
	- Service response time
	- Transaction duration
	- Time to the first response
	- Time to complete return
- Traffic
	- \# HTTP requests per second
	- \# Requests for static vs. dynamic content
	- Network I/O
	- \# Concurrent sessions
	- \# Transactions per second
	- \# of retrievals per second
	- \# of active requests
	- \# of write ops
	- \# of read ops
	- \# of active connections
- Saturation
	- % memory utilization
	- % thread pool utilization
	- % cache utilization
	- % disk utilization
	- % CPU utilization
	- Disk quota
	- Memory quota
	- \# of available connections
	- and \# of users on the system
- Errors
	- Wrong answers or incorrect content
	- \# 400/500 HTTP codes
	- \# failed requests
	- \# exceptions
	- \# stack traces
	- servers that fail liveness checks
	- And \# dropped connections
#### Service Level Indicator (SLI)

SLIs, are carefully selected monitoring metrics that measure one aspect of a service's reliability. Ideally, SLIs should have a close linear relationship with your users' experience of that reliability, and we recommend expressing them as the ratio of two numbers: the number of good events divided by the count of all valid events.

#### Service level objective (SLO)

combines a service level indicator with target reliability. If you express your SLIs as is commonly recommended, your SLOs will generally be somewhere just short of 100%, for example, 99.9%, or "three nines."

##### S.M.A.R.T

- Specific
	  A question such as “Is the site fast enough for you?” is not specific; it's subjective. A statement such as “The 95th percentile of results are returned in under 100 milliseconds” is specific.
- Measurable
	  A lot of monitoring is numbers, grouped over time, with math applied. An SLI must be a number or a delta; something we can measure and place in a mathematical equation.
- Achievable
- Relevant
- Time-bound
	  Do you want a service to be 99% available? That’s fine. Is that per year? Per month? Per day? Does the calculation look at specific windows of set time, from Sunday to Sunday for example, or is it a rolling period of the last seven days? It can't be measured accurately if we don't know the answers to those questions.

#### Service Level Agreements (SLA)

commitments made to your customers that your systems and applications will have only a certain amount of “downtime.” An SLA describes the minimum levels of service that you promise to provide to your customers and what happens when you break that promise. If your service has paying customers, an SLA may include some way of compensating them with refunds or credits when that service has an outage that is longer than this agreement allows. To give you the opportunity to detect problems and take remedial action before your reputation is damaged, your alerting thresholds are often substantially higher than the minimum levels of service documented in your SLA.

![Attachments/Pasted image 20230308005725.png](/img/user/Attachments/Pasted%20image%2020230308005725.png)

![Attachments/Pasted image 20230308010212.png](/img/user/Attachments/Pasted%20image%2020230308010212.png)
### Cloud Monitoring

### Cloud Logging

### Error Reporting

![Attachments/Pasted image 20230308010715.png](/img/user/Attachments/Pasted%20image%2020230308010715.png)

### Cloud Trace

![Attachments/Pasted image 20230308010651.png](/img/user/Attachments/Pasted%20image%2020230308010651.png)
### Cloud Profiler

![Attachments/Pasted image 20230308010630.png](/img/user/Attachments/Pasted%20image%2020230308010630.png)
### Dataflow

### Pub/Sub

## Bare Metal Solution

## Migration
![Attachments/Pasted image 20230312204133.png](/img/user/Attachments/Pasted%20image%2020230312204133.png)

![Attachments/Pasted image 20230312205820.png](/img/user/Attachments/Pasted%20image%2020230312205820.png)

![Attachments/Pasted image 20230312205835.png](/img/user/Attachments/Pasted%20image%2020230312205835.png)

## Cheat sheet
![Attachments/Pasted image 20230312205850.png](/img/user/Attachments/Pasted%20image%2020230312205850.png)