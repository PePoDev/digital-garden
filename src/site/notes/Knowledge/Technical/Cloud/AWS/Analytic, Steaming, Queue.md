---
{"sticker":null,"dg-publish":true,"permalink":"/knowledge/technical/cloud/aws/analytic-steaming-queue/","dgPassFrontmatter":true}
---

## Kinesis
- 
## SQS
- Type of service communication
![Analytic, Steaming, Queue-2023-11-23.png](/img/user/Attachments/Analytic,%20Steaming,%20Queue-2023-11-23.png)
- Overview
![Analytic, Steaming, Queue-2023-11-23-1.png](/img/user/Attachments/Analytic,%20Steaming,%20Queue-2023-11-23-1.png)
- Producer
	- Produced to SQS using the SDK (SendMessage API)
	- The message persists in SQS until a consumer deletes it
- Consumer
	- Poll SQS for messages (receive up to 10 messages at a time)
	- Delete the messages using the `DeleteMessageAPI`
- Type of the SQS
	- Standard Queue (Oldest, over 10 years old)
		- Unlimited throughput, unlimited number of messages in the queue
		- Default retention of messages 4 days, max 14 days
		- Low latency (<10 ms on publish and receive)
		- Limitation of 256KB per message sent
		- Can have duplicate messages (at least once delivery, occasionally)
		- Can have out-of-order messages (best-effort ordering)
- Scaling
![Analytic, Steaming, Queue-2023-11-23-2.png](/img/user/Attachments/Analytic,%20Steaming,%20Queue-2023-11-23-2.png)
- Features
	- Message Visibility Timeout
		- After a message is polled by a consumer, It becomes invisible to other consumers
		- The default is 30 seconds
		- If a message is not processed within the visibility timeout, It will be processed twice
		- A consumer could call the ChangeMessageVisibility API to get more time
		- If visibility timeout is high (hours), and the consumer crashes, re-processing will take time
		- If visibility timeout is too low (seconds), may get duplicates
	- Long polling
		- When a consumer requests messages from the queue, it can optionally `wait` for messages to arrive if there are none in the queue
		- LongPolling decreases the number of API calls made to SQS while increasing the efficiency and latency of your application
		- The wait time can be between 1 sec to 20 sec
		- Long polling is preferable to short polling
		- Long polling can be enabled at the queue level or at the API level using WaitTimeSeconds
- Security
	- In-flight encryption using HTTPS API
	- At-rest encryption using KMS keys
	- Client-side encryption
	- Access Controls by IAM policies
	- SQS Access Policies (similar to S3 bucket policies)
		- Useful for cross-account access
		- Useful for allowing other services to write to an SQS queue
## SNS
- 
## Amazon MQ
- 
