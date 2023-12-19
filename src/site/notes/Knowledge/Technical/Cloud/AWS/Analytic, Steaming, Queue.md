---
{"dg-publish":true,"permalink":"/knowledge/technical/cloud/aws/analytic-steaming-queue/","noteIcon":""}
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
- Use-cases
	- Use as buffer to database writes ![Analytic, Steaming, Queue-2023-11-29.png](/img/user/Attachments/Analytic,%20Steaming,%20Queue-2023-11-29.png)
	- Decouple between application tiers
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
		- Long polling can be enabled at the queue level or at the API level using `WaitTimeSeconds`
	- FIFO Queue
		- Limited throughput 300 msg/s without batching, 300 msg/s with batching
		- Exactly-once send capability (by removing duplicates)
- Security
	- In-flight encryption using HTTPS API
	- At-rest encryption using KMS keys
	- Client-side encryption
	- Access Controls by IAM policies
	- SQS Access Policies (similar to S3 bucket policies)
		- Useful for cross-account access
		- Useful for allowing other services to write to an SQS queue
## SNS
![Analytic, Steaming, Queue-2023-11-29-1.png](/img/user/Attachments/Analytic,%20Steaming,%20Queue-2023-11-29-1.png)
- Up to 12,500,000 subscriptions per topic
- 100,000 topics limit
- Subscribers
	- Emails
	- SMS & Mobile Notifications
	- HTTP(S) Endpoints
	- SQS
	- Lambda
	- Kinesis Data Firehose
- Many AWS Services can send data directly to SNS
	- CloudWatch Alarms
	- AWS Budgets
	- Lambda
	- Auto Scaling Group (Notifications)
	- S3 Bucket (Events)
	- DynamoDB
	- CloudFormation (State Changes)
	- AWS DMS (New Replica)
	- RDS Events
- Publish
	- Topic Publish (SDK)
	- Direct Publish (mobile apps SDK)
- Security
	- Encryption
		- In-flight encryption using HTTPS API
		- At-rest encryption using KMS keys
		- Client-side encryption if the client wants to perform encryption/decryption itself
	- Access Controls
		- IAM policies to regulate access to the SNS API
	- SNS Access Policies (Similar to S3 bucket policies)
		- Useful for cross-account access to SNS topics
		- Useful for allowing other services to write to an SNS topic
- FIFO
	- Ordering by Message Group ID (All message in the same group are ordered)
	- Deduplication using a Deduplication ID or Content Based Deduplication
	- Same throughput as SQS FIFO
- Message Filtering
	- JSON policy used to filter message sent to SNS topic's subscriptions
	- If a subscription doesn't have a filter policy, It receives every message![Analytic, Steaming, Queue-2023-11-29-3.png](/img/user/Attachments/Analytic,%20Steaming,%20Queue-2023-11-29-3.png)
## SNS + SQS: Fan Out Pattern
![Analytic, Steaming, Queue-2023-11-29-2.png](/img/user/Attachments/Analytic,%20Steaming,%20Queue-2023-11-29-2.png)
- Push once in SNS, Receive in all SQS queues
- Fully decoupled, No data loss
- Ability to add more SQS subscribers over time
## Amazon MQ
- 
