---
{"dg-publish":true,"permalink":"/knowledge/technical/cloud/google-cloud/anthos/","dgPassFrontmatter":true}
---

- Application management platform
- The abstraction that builds on container orchestrations and hybrid and multi-cloud implementation
- Addresses challenges of managing applications and services across infrastructures on-premises and in multiple clouds
- Centralized management of configuration as code
- A single view of all cluster infrastructure and application
- Instrumentation of code using Anthos Service Mesh
## Deployment Options
### Google Cloud Deployment
- GKE components
- Anthos Service Mesh
- Anthos Config Management
- Cloud Run
- Multi cluster ingress
- Binary Authorization
### On-premise deployment & AWS
- Anthos clusters
- Anthos Config Management
- Anthos UI & Dashboard
### Attached Clusters Deployment
- Anthos Service Mesh
- Anthos Config Management
- Anthos UI & Dashboard
## Multi-Cluster Ingress
- Cloud-based multi-cloud ingress controller for GKE clusters
- Google hosted
- Share load-balancing resources across clusters
- Support multi-regional cluster
- Proximity-based routing
- Transparent cluster migration during upgrades or rebuilds
- Architecture
	- Multi-Cluster Ingress Controller - Globally distributed control plane running outside of your clusters
	- Config Cluster - GKE Cluster running on Google Cloud, configured with Multi-Cluster Ingress resources
	- Fleet - A domain that groups clusters and infrastructure and applies consistent policies
	- Member cluster - Kubernetes cluster registered to a fleet
## Anthos Service Mesh
- Service Mesh
	- A service mesh controls how parts of an application communicate and share data
	- Dedicated infrastructure layer
	- Requests to services are routed through proxies, also known as sidecars
	- Proxies implement policies to support a service, such as security or logging
	- Microservices don't need to implement these features within the service
- Based on Istio
- Provides for Traffic Management, Observability, and Security
## Cloud Run for Anthos
- Compute service for stateless containers