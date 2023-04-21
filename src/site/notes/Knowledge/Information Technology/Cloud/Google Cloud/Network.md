---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/network/","dgPassFrontmatter":true}
---

## Virtual Private Cloud
A secure, individual, private cloud-computing model hosted within a public cloud. 

> Networks are global and subnets are regional.

![Attachments/Pasted image 20230312210847.png](/img/user/Attachments/Pasted%20image%2020230312210847.png)

- Support to expand subnet without recreating instance
- Can expand but not shrink
- can convert from auto to custom mode

![Attachments/Pasted image 20230312223219.png](/img/user/Attachments/Pasted%20image%2020230312223219.png)

![Attachments/Pasted image 20230312223933.png](/img/user/Attachments/Pasted%20image%2020230312223933.png)

#### Cloud External IP Addresses
#### Cloud Router
- lets other networks and Google VPC, exchange route information over the VPN using the Border Gateway Protocol
- Using this method, if you add a new subnet to your Google VPC, your on-premises network will automatically get routes to it
- But using the internet to connect networks isn't always the best option for everyone, either because of security concerns or because of bandwidth reliability
#### Cloud Firewall Rules
- Stateful
- Priority 0-65535 (0 is highest)
## Shared VPC
- Use IAM roles for delegated administration
- Required an organization
- Required roles
	- Organization Admin
		- Nominates Shared VPC Admin (compute.xpnAdmin)
	- Shared VPC Admin
		- Enables Shared VPC for host project
		- Attached service project
		- Delegates access to some or all subnets in the Shared VPC network (compute.networkUser)
	- Service Project Admin
		- Network User
		- Control over service project resources
			- Compute Instance Admin
			- Project Owner
		- Create resources in Shared VPC
			- VM instances
			- Instance templates and groups
			- Static internal IP
			- Load balancer

![Pasted image 20230327201322.png](/img/user/Attachments/Pasted%20image%2020230327201322.png)
## VPC Peering
- Can be the same or different organizations
- Subnet ranges can't overlap
- Network admin for each VPC must approve the peering requests
![Attachments/Pasted image 20230323004515.png](/img/user/Attachments/Pasted%20image%2020230323004515.png)
## Shared VPC vs VPC Peering
![Attachments/Pasted image 20230323005240.png](/img/user/Attachments/Pasted%20image%2020230323005240.png)
## Network Tier
### Premium Tier
- Premium Tier delivers traffic over Google’s well-provisioned, low-latency, highly reliable global network
- This network consists of an extensive global private fiber network with over [100 points of presence (POPs)](https://peering.google.com/#/) across the globe
![Pasted image 20230404151028.png](/img/user/Attachments/Pasted%20image%2020230404151028.png)
### Standard Tier
- Standard Tier is a new lower-cost offering
- This tier provides network quality that is comparable to other public cloud providers (but lower than Premium Tier) and regional network services such as Regional Load Balancing with one VIP per region
- The standard tier is priced lower than the Premium because your traffic between Google Cloud and your end-user (Internet) is delivered over transit (ISP) networks instead of Google’s network
![Pasted image 20230404151042.png](/img/user/Attachments/Pasted%20image%2020230404151042.png)
## Service Directory
- Managed service to publish, discover, and connect to services
- More dynamic implementation of services means changing IP addresses
- Service Directory tracks changes, eliminates the need to manually update DNS records
## Load balancer
![Pasted image 20230415191300.png](/img/user/Attachments/Pasted%20image%2020230415191300.png)
- Global Cloud Load Balancing
	- Use a single, global anycast IP address
	- No pre-warming is required
	- VM is selected based on proximity and capacity
	- Traffic enters Google's Network as close as possible to the user
- Load balancer types
	- Global HTTP(s)
		- Target HTTP(S) proxy
		- Client SSL session terminates at the load balancer
		- One signed SSL certificate installed (minimum)
		- Support the QUIC transport layer protocol
	- Global SSL Proxy
		- Global load balancing for encrypted, non-HTTP traffic
		- Terminates SSL session at LB layer
		- IPv4 or IPv6 clients
		- Intelligent routing
		- Certificate management
		- Security patching
		- SSL policies
	- Global TCP Proxy
		- Global load balancing for encrypted, non-HTTP traffic
		- Terminates TCP session at LB layer
		- IPv4 or IPv6 clients
		- Intelligent routing
		- Security patching
	- Regional Internal TCP/UDP
		- Uses lightweight load balancing built on top of Andromeda
		- Private load balancing
		- RFC 1918 IP address
		- Reduced latency, Simpler configuration
		- Software-defined, fully distributed load balancing
	- Regional Network TCP/UDP
		- Non-proxied load balancer (all traffic is passed through)
		- Forwarding rules (IP protocol data)
		- Traffic
			- UDP
			- TCP/SSL ports
		- Architecture
			- Backend service-based
			- Target pool-based
	- Regional Internal HTTP(S)
		- Private load balancing
		- RFC 1918 IP address
		- HTTP, HTTPS, or HTTP/2 protocols
		- Based on open source Envoy proxy
- SSL
	- Required for HTTP(S) load balancing
	- Up to 15 SSL certificates (per target proxy)
	- Create an SSL certificate resource

![Pasted image 20230415191048.png](/img/user/Attachments/Pasted%20image%2020230415191048.png)

![Pasted image 20230415191200.png](/img/user/Attachments/Pasted%20image%2020230415191200.png)

![Attachments/Pasted image 20230323184230.png](/img/user/Attachments/Pasted%20image%2020230323184230.png)
### Backend services
- Health check
- Session affinity (optional)
- Time out setting (default 30s)
- One or more backends
	- An instance group (managed or unmanaged)
	- A balancing mode (CPU utilization or RPS)
	- A capacity scaler (ceiling % of CPU/Rate targets)
- Any changes to back-end services are not instantaneous, it takes several minutes to propagate throughout the network
### Backend Buckets
![Attachments/Pasted image 20230323190454.png](/img/user/Attachments/Pasted%20image%2020230323190454.png)
### Network Endpoint Groups (NEG)
- Group of backend endpoints or services
- type of NEGs
	- Zonal
	- Internal
	- Serverless
	- Hybrid connectivity
### Example Diagram
![Attachments/Pasted image 20230323185315.png](/img/user/Attachments/Pasted%20image%2020230323185315.png)

![Attachments/Pasted image 20230323192835.png](/img/user/Attachments/Pasted%20image%2020230323192835.png)

![Attachments/Pasted image 20230323202456.png](/img/user/Attachments/Pasted%20image%2020230323202456.png)
### Choosing LB
![Attachments/Pasted image 20230323213435.png](/img/user/Attachments/Pasted%20image%2020230323213435.png)

![Attachments/Pasted image 20230323213700.png](/img/user/Attachments/Pasted%20image%2020230323213700.png)
## Cloud CDN
- 100% Uptime SLA
- Caches content at the edge of Google's network
- Automatically logged within Google Cloud (Cache Hit, Cache Miss)
- Enable Cloud CDN with a simple checkbox when setting up the backend service
- Minimum `max-age=300` (5 minutes) 
- Cache modes
	- Control the factors that determine whether or not
	- USE_ORIGIN_HEADERS
	- CACHE_ALL_STATIC
	- FORCE_CACHE_ALL
- Using Versioned URLs to update content
![Pasted image 20230415191233.png](/img/user/Attachments/Pasted%20image%2020230415191233.png)
## Network Intelligence Center
- Visualize network topology
- Test network connectivity
![Pasted image 20230415191415.png](/img/user/Attachments/Pasted%20image%2020230415191415.png)
## Cloud Interconnect and peering services
![Attachments/Pasted image 20230323000001.png](/img/user/Attachments/Pasted%20image%2020230323000001.png)

- Dedicated connections provide a direct connection to Google's network
- Shared connections for white a connection to Google's network through a partner
- Layer 2 connections use a VLAN that pipes directly into your GCP environment providing connectivity to internal IP addresses in the RFC 1918 address base
- Layer 3 connections provide access to G Suite services, YouTube, and Google Cloud APIs using public IP addresses
### Cloud VPN
- Securely connects your on-premises network to your Google Cloud VPC network
- Useful for low-volume data connections
- 99.9% SLA
- Supports
	- Site-to-Site VPN
	- Static routes
	- Dynamic routes (Cloud Router)
	- IKEv1 and IKEv2 ciphers
- Doesn’t support "dial in" with client VPN software
- MTU for on-premises VPN gateway cannot be greater than 1460 bytes

![Attachments/Pasted image 20230321225933.png](/img/user/Attachments/Pasted%20image%2020230321225933.png)
### HA VPN
- SLA 99.99%
- Must properly configure two or four tunnels from your HA VPN gateway to your peer VPN gateway or to another HA VPN gateway
- Automatically chooses two external IP addresses
	- Supports multiple tunnels
	- VPN tunnels connected to HA VPN gateways must use dynamic (BGP) routing
- Supports site-to-site VPN for different topologies/configuration scenarios
	- An HA VPN gateway to peer VPN devices
	- An HA VPN gateway to an AWS virtual private gateway
	- Two HA VPN gateways connected to each other

![Attachments/Pasted image 20230322132327.png](/img/user/Attachments/Pasted%20image%2020230322132327.png)

![Attachments/Pasted image 20230322132523.png](/img/user/Attachments/Pasted%20image%2020230322132523.png)

![Attachments/Pasted image 20230322132702.png](/img/user/Attachments/Pasted%20image%2020230322132702.png)
### Direct Peering
- Peering means putting a router in the same public data center as a Google point of presence and using it to exchange traffic between networks
- Google has more than 100 points of presence around the world
- Broad-reaching edge network locations
- Exchange BGP routes
- Reach all of Google's services
- No SLA
### Carrier Peering
- Customers who aren’t already in a point of presence can work with a partner in the Carrier Peering program to get connected
- Carrier peering gives you direct access from your on-premises network through a service provider's network to Google Workspace and to Google Cloud products that can be exposed through one or more public IP addresses
- No SLA
### Dedicated Interconnect
![Attachments/Pasted image 20230323000137.png](/img/user/Attachments/Pasted%20image%2020230323000137.png)
- Dedicated Interconnect provides direct physical connections between your on-premises network and Google's network
- This enables you to transfer large amounts of data between networks, which can be more cost-effective than purchasing additional bandwidth over the public internet
- If getting the highest uptimes for interconnection is important, using Dedicated Interconnect would be a good solution
- This option allows for one or more direct, private connections to Google. If these connections have topologies that meet Google’s specifications, they can be covered by an SLA of up to 99.99%
- Also, these connections can be backed up by a VPN for even greater reliability
- Can have up to eight links to achieve multiples of 10 Gbps but 10 Gbps is the minimum capacity
- The BETA provides 100 Gbps per link with a maximum of two links
### Partner Interconnect
![Attachments/Pasted image 20230323001945.png](/img/user/Attachments/Pasted%20image%2020230323001945.png)
- Provides connectivity between an on-premises network and a VPC network through a supported service provider
- A Partner Interconnect connection is useful if a data center is in a physical location that can't reach a Dedicated Interconnect colocation facility, or if the data needs don’t warrant an entire 10 GigaBytes per second connection
- Partner Interconnect can be configured to offer a 99.9% or a 99.99% uptime SLA
### Comparison

![Attachments/Pasted image 20230323002552.png](/img/user/Attachments/Pasted%20image%2020230323002552.png)

![Attachments/Pasted image 20230323003356.png](/img/user/Attachments/Pasted%20image%2020230323003356.png)
### Choosing
![Attachments/Pasted image 20230323003530.png](/img/user/Attachments/Pasted%20image%2020230323003530.png)

![Attachments/Pasted image 20230323003616.png](/img/user/Attachments/Pasted%20image%2020230323003616.png)
