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
#### Cloud Routes
Cloud Router lets other networks and Google VPC, exchange route information over the VPN using the Border Gateway Protocol. Using this method, if you add a new subnet to your Google VPC, your on-premises network will automatically get routes to it. But using the internet to connect networks isn't always the best option for everyone, either because of security concerns or because of bandwidth reliability.

#### Cloud Firewall Rules
## Shared VPC
![Attachments/Pasted image 20230323004140.png](/img/user/Attachments/Pasted%20image%2020230323004140.png)
## VPC Peering
![Attachments/Pasted image 20230323004515.png](/img/user/Attachments/Pasted%20image%2020230323004515.png)
## Shared VPC vs VPC Peering
![Attachments/Pasted image 20230323005240.png](/img/user/Attachments/Pasted%20image%2020230323005240.png)
## Load balancer
- Global HTTP(s)
- Global SSL Proxy
- Global TCP Proxy
- Regional Internal TCP/UDP
- Regional Network TCP/UDP
- Regional Internal HTTP(S)

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
