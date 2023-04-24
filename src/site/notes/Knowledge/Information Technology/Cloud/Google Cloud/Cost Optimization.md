---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/cost-optimization/","dgPassFrontmatter":true}
---

## GKE
- Scale down the service that didn't necessarily in the non-prod environment
- Use namespace to separate the service to track the resource usage
- Use `resource quota` and `limit range` to enforce resource limitation
### Over-provision
- Aka. Bin packing problem
- You don't want it to hit 100%, so you could choose a buffer of 15% to keep a safe distance
- Then, the traffic variable in the formula would be the percentage of traffic growth estimated in the next 2 to 3 minutes
- In the load test you ran earlier, 0% to 150% was a bit of an extreme growth example, so instead imagine a more average traffic growth of 30%
![Cost Optimization-2023-04-24.png](/img/user/Attachments/Cost%20Optimization-2023-04-24.png)
### Committed-use discount
### Preemptible
## Cost planning
![Cost Optimization-2023-04-24-1.png](/img/user/Attachments/Cost%20Optimization-2023-04-24-1.png)

![Cost Optimization-2023-04-24-2.png](/img/user/Attachments/Cost%20Optimization-2023-04-24-2.png)

![Cost Optimization-2023-04-24-3.png](/img/user/Attachments/Cost%20Optimization-2023-04-24-3.png)

![Cost Optimization-2023-04-24-4.png](/img/user/Attachments/Cost%20Optimization-2023-04-24-4.png)

![Cost Optimization-2023-04-24-5.png](/img/user/Attachments/Cost%20Optimization-2023-04-24-5.png)

![Cost Optimization-2023-04-24-6.png](/img/user/Attachments/Cost%20Optimization-2023-04-24-6.png)

![Cost Optimization-2023-04-24-7.png](/img/user/Attachments/Cost%20Optimization-2023-04-24-7.png)

![Cost Optimization-2023-04-24-8.png](/img/user/Attachments/Cost%20Optimization-2023-04-24-8.png)

![Cost Optimization-2023-04-24-9.png](/img/user/Attachments/Cost%20Optimization-2023-04-24-9.png)

![Cost Optimization-2023-04-24-10.png](/img/user/Attachments/Cost%20Optimization-2023-04-24-10.png)

![Cost Optimization-2023-04-24-11.png](/img/user/Attachments/Cost%20Optimization-2023-04-24-11.png)

![Cost Optimization-2023-04-24-12.png](/img/user/Attachments/Cost%20Optimization-2023-04-24-12.png)
### Products Which Can Generate Big Logs
- VPC Flow Logs
	- Percentage
	- Message type (CIDR)
- HTTP 200 OK from requests
- Load balancer
- Logging agent on Compute Engine or AWS
- The write operation 9in the Cloud Logging API