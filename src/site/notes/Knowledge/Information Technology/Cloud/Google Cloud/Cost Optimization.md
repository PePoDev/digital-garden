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
![Pasted image 20230404173904.png](/img/user/Attachments/Pasted%20image%2020230404173904.png)
### Committed-use discount
### Preemptible
## Cost planning
![Pasted image 20230415223626.png](/img/user/Attachments/Pasted%20image%2020230415223626.png)

![Pasted image 20230415223650.png](/img/user/Attachments/Pasted%20image%2020230415223650.png)

![Pasted image 20230415223705.png](/img/user/Attachments/Pasted%20image%2020230415223705.png)

![Pasted image 20230415223732.png](/img/user/Attachments/Pasted%20image%2020230415223732.png)

![Pasted image 20230415223746.png](/img/user/Attachments/Pasted%20image%2020230415223746.png)

![Pasted image 20230415223847.png](/img/user/Attachments/Pasted%20image%2020230415223847.png)

![Pasted image 20230415223901.png](/img/user/Attachments/Pasted%20image%2020230415223901.png)

![Pasted image 20230415223920.png](/img/user/Attachments/Pasted%20image%2020230415223920.png)

![Pasted image 20230415224003.png](/img/user/Attachments/Pasted%20image%2020230415224003.png)

![Pasted image 20230415223939.png](/img/user/Attachments/Pasted%20image%2020230415223939.png)

![Pasted image 20230415224016.png](/img/user/Attachments/Pasted%20image%2020230415224016.png)

![Pasted image 20230415224038.png](/img/user/Attachments/Pasted%20image%2020230415224038.png)
