---
{"dg-publish":true,"permalink":"/knowledge/technical/observability/observability/","noteIcon":""}
---

## Pages

- [[Knowledge/Technical/Observability/Datadog\|Datadog]]


## Monitoring vs Observability
- Monitoring
	- Monitoring is the process of gathering data to understand what's going on inside of your infrastructure
- Observability
	- Observability is taking the same data that you've collected and moving beyond "What is happening?" to "Why is it happening?"
## 3 Pillar of observability
![Observability-2024-06-13.png](/img/user/Attachments/Observability-2024-06-13.png)
### Metrics
- These data points are numerical values that can track anything about your environment over time
	- example: latency, error rates, user signups
### Logs
- A computer-generated file that contains time-stamped information about the usage of that system (a bulky piece or length of a cut or fallen tree)
- Why do we collect Logs?
	- Compliance
	- Insight
	- Security
### Traces
- Used to track the time spent by an application processing a request and the status of this request
	- Why do we collect Trances?
		- Microservices
		- Optimization
		- Troubleshooting
	- What is Span? ![Observability-2024-06-14.png](/img/user/Attachments/Observability-2024-06-14.png)
## Monitoring
- Monitoring is the act of paying attention to the patterns that your metrics are telling you. It's about analyzing your data and acting on it
	- What do we Monitor?
		- Performance
		- Security
		- Usage
## Alerting
- Alerts are simply setting a threshold in a monitor, When that threshold is breached, a notification is sent to the designated recipient
- Alert Fatigue
	- arises from over-alerting, it's important to only alert team members when something actionable needs to be done
## References
- https://learn.datadoghq.com
