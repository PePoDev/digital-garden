---
{"dg-publish":true,"candidate-id":"547c5bbe-4d3b-4dbf-b066-6c60e3770e75","permalink":"/knowledge/technical/cloud/google-cloud/google-cloud/","dgPassFrontmatter":true}
---

## Links
- [Assessment Registration](https://www.webassessor.com/wa.do?page=publicHome&branding=GOOGLECLOUD)
- [Google Cloud Skills Boost for Partners](https://partner.cloudskillsboost.google)
- [Google Cloud Skills Boost](https://www.cloudskillsboost.google/profile/paths)
- [Google Cloud Partner Technical Training](https://rsvp.withgoogle.com/events/partner-learning/google-cloud-certifications)
- [Google Cloud Pricing Calculator](https://cloud.google.com/products/calculator)
- [Partner Certification Kickstart | Google Cloud](https://inthecloud.withgoogle.com/pck-page/register.html)
## Certificates
- [x] Cloud Digital Leader #certificate 🔼 ✅ 2023-04-20
- [/] Associate Cloud Engineer #certificate 🔼
- [x] Professional Cloud Architect #certificate ⏫ ✅ 2023-05-05
- [ ] Professional Cloud Developer #certificate
- [ ] Professional Cloud DevOps Engineer #certificate
- [ ] Professional Data Engineer #certificate
- [ ] Professional Cloud Security Engineer #certificate
- [ ] Professional Cloud Network Engineer #certificate
- [ ] Professional Collaboration Engineer #certificate
- [ ] Professional Machine Learning Engineer #certificate
- [ ] Professional Cloud Database Engineer #certificate
- [ ] Google Workspace Administrator #certificate
## Contents

- [[Knowledge/Technical/Cloud/Google Cloud/Analytics\|Analytics]]
- [[Knowledge/Technical/Cloud/Google Cloud/Anthos\|Anthos]]
- [[Knowledge/Technical/Cloud/Google Cloud/Automation\|Automation]]
- [[Knowledge/Technical/Cloud/Google Cloud/Compliance\|Compliance]]
- [[Knowledge/Technical/Cloud/Google Cloud/Compute\|Compute]]
- [[Knowledge/Technical/Cloud/Google Cloud/Cost Optimization\|Cost Optimization]]
- [[Knowledge/Technical/Cloud/Google Cloud/IAM\|IAM]]
- [[Knowledge/Technical/Cloud/Google Cloud/IoT\|IoT]]
- [[Knowledge/Technical/Cloud/Google Cloud/Migration\|Migration]]
- [[Knowledge/Technical/Cloud/Google Cloud/ML\|ML]]
- [[Knowledge/Technical/Cloud/Google Cloud/Monitoring\|Monitoring]]
- [[Knowledge/Technical/Cloud/Google Cloud/Network\|Network]]
- [[Knowledge/Technical/Cloud/Google Cloud/Organization\|Organization]]
- [[Knowledge/Technical/Cloud/Google Cloud/Resource Management\|Resource Management]]
- [[Knowledge/Technical/Cloud/Google Cloud/Security\|Security]]
- [[Knowledge/Technical/Cloud/Google Cloud/Storage\|Storage]]



> [!tip]+
> Cloud computing is a way of using information technology (IT) that has these five equally important traits.
> First, customers get computing resources that are on-demand and self-service.
> Second, customers get access to those resources over the internet, from anywhere they have a connection.
> Third, the cloud provider has a big pool of those resources and allocates them to users out of that pool. That allows the provider to buy in bulk and pass the savings on to the customers.
> Fourth, the resources are elastic–which means they’re flexible, so customers can be.
> Finally, customers pay only for what they use, or reserve as they go.
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

![Google Cloud-2023-04-24.png](/img/user/Attachments/Google%20Cloud-2023-04-24.png)

- In our founding decade, Google became the first major company to be carbon neuapitral.
- In our second decade, we were the first company to achieve 100% renewable energy.
- By 2030, we aim to be the first major company to operate completely carbon-free.

![Google Cloud-2023-04-24-1.png](/img/user/Attachments/Google%20Cloud-2023-04-24-1.png)

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

![Google Cloud-2023-04-24-2.png](/img/user/Attachments/Google%20Cloud-2023-04-24-2.png)
## Pricing & Billing
- Google was the first major cloud provider to deliver per-second billing.
- Automatically applied sustained-use discounts are automatic discounts you get for running a virtual machine instance for a significant portion of the billing month. Specifically, when you run an instance for more than 25% of a month, Compute Engine automatically gives you a discount for every incremental minute you use for that instance.

https://cloud.google.com/products/calculator

![Google Cloud-2023-04-24-3.png](/img/user/Attachments/Google%20Cloud-2023-04-24-3.png)
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
2. Cloud SDK and Cloud Shell (gcloud, kubectl, gsutil, bq)
3. APIs
4. Cloud Mobile App
### Cloud Endpoints
- Distributed API management system
- Provides an API console, hosting, logging, monitoring, and other features
- Use with any APIs that support the OpenAPI specification
- Supports applications running in App Engine, GKE, and Compute Engine
- Clients include Android, iOS, and Javascript
- Protect and monitor your public APIs
- Integrates with Identity Platform
- Control who has access to your API
### API Gateway
- Backend implementations can vary for a single service provider
- Provide secure access to your backend services through a well-defined REST API
- Clients consume your REST APIs to implement standalone apps
### Apigee API Management
![Google Cloud-2023-04-24-8.png](/img/user/Attachments/Google%20Cloud-2023-04-24-8.png)
- Design, secure, publish, analyze, monitor, monetize, and scale APIs anywhere
- Manage Complete API life cycle
- Provides AI-powered API monitoring (Get actionable insights)
- Create Developer Portals
	- Allow developers to easily explore the APIs, get API keys
- Expose ML models as APIs
- Specific focus on business problems like rate limiting quotas and analytics
- Many Apigee Edge users provide a software service to other companies
- Backend services for Apigee Edge don't need to be in Google Cloud
### Dataflow

### Pub/Sub
## Support
- Support options
	- Technical Support
		- When something isn't working right
	- Billing Support
		- Help with your bill and purchasing reserved instance
	- Role-based Support
		- More predictable rates and a flexible configuration
	- Enterprise Support
		- Working directly with TAM (Technical Account Management) Contact
- Support level
	- Basic
		- Free
		- Least Amount of Options
	- Standard
		- Unlimited access to support
		- 4-hour response time to priority 2 cases
		- Receive support during local business hours, Monday - Friday
	- Enhanced
		- Guaranteed 1 hour response to priority 1 cases
		- Ability to escalate cases for additional attention
	- Premium
		- Guaranteed 15 minute response time to priority 1 cases
		- A number of value add services
## Bare Metal Solution

## Migration
![Google Cloud-2023-04-24-4.png](/img/user/Attachments/Google%20Cloud-2023-04-24-4.png)

![Google Cloud-2023-04-24-5.png](/img/user/Attachments/Google%20Cloud-2023-04-24-5.png)

![Google Cloud-2023-04-24-6.png](/img/user/Attachments/Google%20Cloud-2023-04-24-6.png)

## Cheat sheet
![Google Cloud-2023-04-24-7.png](/img/user/Attachments/Google%20Cloud-2023-04-24-7.png)