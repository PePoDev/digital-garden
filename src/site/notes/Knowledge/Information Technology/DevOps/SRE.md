---
{"dg-publish":true,"permalink":"/knowledge/information-technology/dev-ops/sre/","dgPassFrontmatter":true}
---

## Links
https://sre.google/sre-book/table-of-contents/
https://sre.google/workbook/table-of-contents/
## SRE
![Attachments/Pasted image 20230307225538.png](/img/user/Attachments/Pasted%20image%2020230307225538.png)

### Four Golden Signals
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
### Service Level Indicator (SLI)
SLIs, are carefully selected monitoring metrics that measure one aspect of a service's reliability. Ideally, SLIs should have a close linear relationship with your users' experience of that reliability, and we recommend expressing them as the ratio of two numbers: the number of good events divided by the count of all valid events.

### Service level objective (SLO)
combines a service level indicator with target reliability. If you express your SLIs as is commonly recommended, your SLOs will generally be somewhere just short of 100%, for example, 99.9%, or "three nines."

#### S.M.A.R.T
- Specific
	  A question such as “Is the site fast enough for you?” is not specific; it's subjective. A statement such as “The 95th percentile of results are returned in under 100 milliseconds” is specific.
- Measurable
	  A lot of monitoring is numbers, grouped over time, with math applied. An SLI must be a number or a delta; something we can measure and place in a mathematical equation.
- Achievable
- Relevant
- Time-bound
	  Do you want a service to be 99% available? That’s fine. Is that per year? Per month? Per day? Does the calculation look at specific windows of set time, from Sunday to Sunday for example, or is it a rolling period of the last seven days? It can't be measured accurately if we don't know the answers to those questions.

### Service Level Agreements (SLA)

commitments made to your customers that your systems and applications will have only a certain amount of “downtime.” An SLA describes the minimum levels of service that you promise to provide to your customers and what happens when you break that promise. If your service has paying customers, an SLA may include some way of compensating them with refunds or credits when that service has an outage that is longer than this agreement allows. To give you the opportunity to detect problems and take remedial action before your reputation is damaged, your alerting thresholds are often substantially higher than the minimum levels of service documented in your SLA.

![Attachments/Pasted image 20230308005725.png](/img/user/Attachments/Pasted%20image%2020230308005725.png)

![Attachments/Pasted image 20230308010212.png](/img/user/Attachments/Pasted%20image%2020230308010212.png)
