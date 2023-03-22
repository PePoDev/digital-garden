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

![Attachments/Pasted image 20230320221609.png](/img/user/Attachments/Pasted%20image%2020230320221609.png)

![Attachments/Pasted image 20230320222001.png](/img/user/Attachments/Pasted%20image%2020230320222001.png)
## Cloud Monitoring
![Attachments/Pasted image 20230320222055.png](/img/user/Attachments/Pasted%20image%2020230320222055.png)

- Dynamic config and intelligent defaults
- Platform, system, and application metrics
	- ingests data: Metrics, events, metadata
	- Generates insights through the dashboard, charts, alerts
- Uptime/health checks
- Dashboards
- Alerts
### Workspace
- Determine your monitoring needs upfront
- Consider using separate Workspaces for data and control isolation

![Attachments/Pasted image 20230320222319.png](/img/user/Attachments/Pasted%20image%2020230320222319.png)
## Cloud Logging
- Platform, systems, and application logs
	- API to write to logs
	- 30-day retention
- Log search/view/filter
- Log-based metrics
- Monitoring alerts can be set on log events
- Data can be exported to Cloud Storage, BigQuery, and Pub/Sub
- Export to Object storage, BigQuery, and Pub/Sub
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
- Data
	- App Engine
	- Google HTTP(S) load balancers
	- Applications instrumented with the Cloud Trace SDKs
## Cloud Debugger
- Inspect an application without stopping it or slowing it down significantly
- Capture call stack and local variables of a running application
- Inject logging into a service without stopping it
## Cloud Profiler
- Uses statistical techniques and extremely low-impact instrumentation that runs across all production application instances to provide a complete CPU and heap picture of an application
- Allows developers to analyze applications running anywhere, including Google Cloud, another cloud performs, or on-premises, with support for Java, Go, Python, and NodeJS
- Presents the call hierarchy and resource consumption of the relevant function in an interactive flame graph
