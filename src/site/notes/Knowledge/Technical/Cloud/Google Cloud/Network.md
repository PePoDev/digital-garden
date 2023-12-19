---
{"dg-publish":true,"permalink":"/knowledge/technical/cloud/google-cloud/network/","noteIcon":""}
---

## Virtual Private Cloud
A secure, individual, private cloud-computing model hosted within a public cloud. 
> Networks are global and subnets are regional.
![Network-2023-04-24.png](/img/user/Attachments/Network-2023-04-24.png)
- Support to expand subnet without recreating instance
- Can expand but not shrink
- can convert from auto to custom mode
![Network-2023-04-24-1.png](/img/user/Attachments/Network-2023-04-24-1.png)
![Network-2023-04-24-2.png](/img/user/Attachments/Network-2023-04-24-2.png)
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

![Network-2023-04-24-3.png](/img/user/Attachments/Network-2023-04-24-3.png)
## VPC Peering
- Can be the same or different organizations
- Subnet ranges can't overlap
- Network admin for each VPC must approve the peering requests
![Network-2023-04-24-4.png](/img/user/Attachments/Network-2023-04-24-4.png)
## Shared VPC vs VPC Peering
![Network-2023-04-24-5.png](/img/user/Attachments/Network-2023-04-24-5.png)
## Network Tier
### Premium Tier
- Premium Tier delivers traffic over Google’s well-provisioned, low-latency, highly reliable global network
- This network consists of an extensive global private fiber network with over [100 points of presence (POPs)](https://peering.google.com/#/) across the globe
![Network-2023-04-24-6.png](/img/user/Attachments/Network-2023-04-24-6.png)
### Standard Tier
- Standard Tier is a new lower-cost offering
- This tier provides network quality that is comparable to other public cloud providers (but lower than Premium Tier) and regional network services such as Regional Load Balancing with one VIP per region
- The standard tier is priced lower than the Premium because your traffic between Google Cloud and your end-user (Internet) is delivered over transit (ISP) networks instead of Google’s network
![Network-2023-04-24-7.png](/img/user/Attachments/Network-2023-04-24-7.png)
## Service Directory
- Managed service to publish, discover, and connect to services
- More dynamic implementation of services means changing IP addresses
- Service Directory tracks changes, eliminates the need to manually update DNS records
## Load balancer
![Network-2023-04-24-8.png](/img/user/Attachments/Network-2023-04-24-8.png)
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

![Network-2023-04-24-9.png](/img/user/Attachments/Network-2023-04-24-9.png)

![Network-2023-04-24-10.png](/img/user/Attachments/Network-2023-04-24-10.png)

![Network-2023-04-24-11.png](/img/user/Attachments/Network-2023-04-24-11.png)
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
![Network-2023-04-24-12.png](/img/user/Attachments/Network-2023-04-24-12.png)
### Network Endpoint Groups (NEG)
- Group of backend endpoints or services
- type of NEGs
	- Zonal
	- Internal
	- Serverless
	- Hybrid connectivity
### Example Diagram
![Network-2023-04-24-13.png](/img/user/Attachments/Network-2023-04-24-13.png)

![Network-2023-04-24-14.png](/img/user/Attachments/Network-2023-04-24-14.png)

![Network-2023-04-24-15.png](/img/user/Attachments/Network-2023-04-24-15.png)
### Choosing LB
![Network-2023-04-24-16.png](/img/user/Attachments/Network-2023-04-24-16.png)

![Network-2023-04-24-17.png](/img/user/Attachments/Network-2023-04-24-17.png)
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
![Network-2023-04-24-18.png](/img/user/Attachments/Network-2023-04-24-18.png)
## Network Intelligence Center
- Visualize network topology
- Test network connectivity
![Network-2023-04-24-19.png](/img/user/Attachments/Network-2023-04-24-19.png)
## Cloud Interconnect and peering services
![Network-2023-04-24-20.png](/img/user/Attachments/Network-2023-04-24-20.png)

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

![Network-2023-04-24-21.png](/img/user/Attachments/Network-2023-04-24-21.png)
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

![Network-2023-04-24-22.png](/img/user/Attachments/Network-2023-04-24-22.png)

![Network-2023-04-24-23.png](/img/user/Attachments/Network-2023-04-24-23.png)

![Network-2023-04-24-24.png](/img/user/Attachments/Network-2023-04-24-24.png)
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
![Network-2023-04-24-25.png](/img/user/Attachments/Network-2023-04-24-25.png)
- Dedicated Interconnect provides direct physical connections between your on-premises network and Google's network
- This enables you to transfer large amounts of data between networks, which can be more cost-effective than purchasing additional bandwidth over the public internet
- If getting the highest uptimes for interconnection is important, using Dedicated Interconnect would be a good solution
- This option allows for one or more direct, private connections to Google. If these connections have topologies that meet Google’s specifications, they can be covered by an SLA of up to 99.99%
- Also, these connections can be backed up by a VPN for even greater reliability
- Can have up to eight links to achieve multiples of 10 Gbps but 10 Gbps is the minimum capacity
- The BETA provides 100 Gbps per link with a maximum of two links
### Partner Interconnect
![Network-2023-04-24-26.png](/img/user/Attachments/Network-2023-04-24-26.png)
- Provides connectivity between an on-premises network and a VPC network through a supported service provider
- A Partner Interconnect connection is useful if a data center is in a physical location that can't reach a Dedicated Interconnect colocation facility, or if the data needs don’t warrant an entire 10 GigaBytes per second connection
- Partner Interconnect can be configured to offer a 99.9% or a 99.99% uptime SLA
### Comparison

![Network-2023-04-24-27.png](/img/user/Attachments/Network-2023-04-24-27.png)

![Network-2023-04-24-28.png](/img/user/Attachments/Network-2023-04-24-28.png)
### Choosing
![Network-2023-04-24-29.png](/img/user/Attachments/Network-2023-04-24-29.png)

![Network-2023-04-24-30.png](/img/user/Attachments/Network-2023-04-24-30.png)
