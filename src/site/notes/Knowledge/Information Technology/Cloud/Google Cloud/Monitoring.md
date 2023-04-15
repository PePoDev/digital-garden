---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/monitoring/","dgPassFrontmatter":true}
---

## Google Cloud Operations suite
- previously stackdriver
- Integrated monitoring, logging, diagnostics
- Manages across platforms
	- Google Cloud and AWS
	- Dynamic discovery of Google Cloud with smart defaults
	- Open-source agents and integrations
- Access to powerful data and analytics tools
- Collaboration with third-party software
![Pasted image 20230328221701.png](/img/user/Attachments/Pasted%20image%2020230328221701.png)

![Attachments/Pasted image 20230320222001.png](/img/user/Attachments/Pasted%20image%2020230320222001.png)
## Cloud Monitoring
![Attachments/Pasted image 20230320222055.png](/img/user/Attachments/Pasted%20image%2020230320222055.png)

![Pasted image 20230328221839.png](/img/user/Attachments/Pasted%20image%2020230328221839.png)

- Dynamic config and intelligent defaults
- Platform, system, and application metrics
	- ingests data: Metrics, events, metadata
	- Generates insights through the dashboard, charts, alerts
- Uptime/health checks
- Dashboards
- Alerts
### Ops Agent
- Support Compute Engine and AWS EC2
## Monitoring pyramid
![Pasted image 20230328221611.png](/img/user/Attachments/Pasted%20image%2020230328221611.png)
### Workspace
- Determine your monitoring needs upfront
- Consider using separate Workspaces for data and control isolation

![Pasted image 20230415141243.png](/img/user/Attachments/Pasted%20image%2020230415141243.png)
## Cloud Logging
- Platform, systems, and application logs
	- API to write to logs
	- 30-day retention
- Log search/view/filter
- Log-based metrics
- Monitoring alerts can be set on log events
- Data can be exported to Cloud Storage, BigQuery, and Pub/Sub
- Export to Cloud storage, BigQuery, and Pub/Sub
- Data access logs are retained for 1-3650 days and Admin logs for 400 days
- Logs
	- Cloud Audit Logs
		- Admin activity
		- Data Access
		- System Event
		- Access Transparency
	- Agent Logs
	- Network Logs
		- VPC flow
		- Firewall rules
		- NAT gateway
		- Load Balancer
## Data Studio
- Connect to BigQuery
- Transform raw data into metrics and dimensions
## Error Reporting
- Error dashboard/notification
- Counts analyze and aggregate the crashes in your running cloud services
- Management interface displays the results with sorting and filtering capability
## Cloud Trace
- Displays data/performance insights in near real-time
- Latency reporting
- Per-URL latency sampling
- Automatically analyzes to generate in-depth latency reports
- Support
	- App Engine
	- Google HTTP(S) load balancers
	- Applications instrumented with the Cloud Trace SDKs
## Cloud Debugger
- Inspect an application without stopping it or slowing it down significantly
- Capture call stack and local variables of a running application
- Inject logging into a service without stopping it
- Increased collaboration by sharing debug session
- Debug snapshots, logpoints, conditional debugging
- Integrations with popular IDEs
## Cloud Profiler
- Uses statistical techniques and extremely low-impact instrumentation that runs across all production application instances to provide a complete CPU and heap picture of an application
- Support for Java, Go, Python, and NodeJS
- Presents the call hierarchy and resource consumption of the relevant function in an interactive flame graph
- Improve performance and reduce costs
- Understand application call patterns
## Service Monitoring
- Understand and troubleshoot intra-service dependencies
- Current support for App Engine, Anthos Service Mesh, and Istio
- Know when you're meeting or breaking SLOs
- Know when you have an error budget to spend
